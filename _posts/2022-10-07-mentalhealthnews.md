---
title: Fetch of Mental Health Sources
layout: default
description: An introductory example of Frontend talking to Backend Java application serving mental health articles.  
permalink: /data/jokes
image: /images/jokes.png
categories: [1.C]
tags: [javascript]
---

<!-- HTML table fragment for page -->
<table>
  <thead>
  <tr>
    <th>Article and Link</th>
    <th>Helpful</th>
    <th>Unhelpful</th>
  </tr>
  </thead>
  <tbody id="result">
    <!-- javascript generated data -->
  </tbody>
</table>

<!-- Script is layed out in a sequence (without a function) and will execute when page is loaded -->
<script>

  // prepare HTML defined "result" container for new output
  const resultContainer = document.getElementById("result");

  // keys for joke reactions
  const HELPFUL = "helpful";
  const UNHELPFUL = "unhelpful";

  // prepare fetch urls
  // const url = "https://flask.nighthawkcodingsociety.com/api/jokes";
  const url = "https://spring.nighthawkcodingsociety.com/api/jokes";
  const get_url = url +"/";
  const like_url = url + "/like/";  // buy reaction
  const jeer_url = url + "/jeer/";  // skip reaction

  // prepare fetch GET options
  const options = {
    method: 'GET', // *GET, POST, PUT, DELETE, etc.
    mode: 'cors', // no-cors, *cors, same-origin
    cache: 'default', // *default, no-cache, reload, force-cache, only-if-cached
    credentials: 'same-origin', // include, same-origin, omit
    headers: {
      'Content-Type': 'application/json'
      // 'Content-Type': 'application/x-www-form-urlencoded',
    },
  };
  // prepare fetch PUT options, clones with JS Spread Operator (...)
  const put_options = {...options, method: 'PUT'}; // clones and replaces method

  // fetch the API
  fetch(get_url, options)
    // response is a RESTful "promise" on any successful fetch
    .then(response => {
      // check for response errors
      if (response.status !== 200) {
          error('GET API response failure: ' + response.status);
          return;
      }
      // valid response will have JSON data
      response.json().then(data => {
          console.log(data);
          for (const row of data) {
            // make "tr element" for each "row of data"
            const tr = document.createElement("tr");

            // td for joke cell
            const item = document.createElement("td");
              item.innerHTML = row.id + ". " + row.item;  // add fetched data to innerHTML

            // td for buy cell with onclick actions
            const helpful = document.createElement("td");
              const helpful_but = document.createElement('button');
              helpful_but.id = helpful+row.id   // establishes a buy JS id for cell
              helpful_but.innerHTML = row.helpful;  // add fetched "buy count" to innerHTML
              helpful_but.onclick = function () {
                // onclick function call with "like parameters"
                reaction(helpful, like_url+row.id, helpful_but.id);  
              };
              helpful.appendChild(helpful_but);  // add "buy button" to buy cell

            // td for skip cell with onclick actions
            const unhelpful = document.createElement("td");
              const unhelpful_but = document.createElement('button');
              unhelpful_but.id = unhelpful+row.id  // establishes a skip JS id for cell
              unhelpful_but.innerHTML = row.unhelpful;  // add fetched "skip count" to innerHTML
              unhelpful_but.onclick = function () {
                // onclick function call with "jeer parameters"
                reaction(unhelpful, jeer_url+row.id, skip_but.id);  
              };
              unhelpful.appendChild(unhelpful_but);  // add "skip button" to skip cell

            // this builds ALL td's (cells) into tr (row) element
            tr.appendChild(item);
            tr.appendChild(helpful);
            tr.appendChild(unhelpful);

            // this adds all the tr (row) work above to the HTML "result" container
            resultContainer.appendChild(tr);
          }
      })
  })
  // catch fetch errors (ie Nginx ACCESS to server blocked)
  .catch(err => {
    error(err + " " + get_url);
  });

  // Reaction function to likes or jeers user actions
  function reaction(type, put_url, elemID) {

    // fetch the API
    fetch(put_url, put_options)
    // response is a RESTful "promise" on any successful fetch
    .then(response => {
      // check for response errors
      if (response.status !== 200) {
          error("PUT API response failure: " + response.status)
          return;  // api failure
      }
      // valid response will have JSON data
      response.json().then(data => {
          console.log(data);
          // Likes or Jeers updated/incremented
          if (type === helpful) // like data element
            document.getElementById(elemID).innerHTML = data.helpful;  // fetched buy data assigned to buy Document Object Model (DOM)
          else if (type === unhelpful) // jeer data element
            document.getElementById(elemID).innerHTML = data.unhelpful;  // fetched skip data assigned to skip Document Object Model (DOM)
          else
            error("unknown type: " + type);  // should never occur
      })
    })
    // catch fetch errors (ie Nginx ACCESS to server blocked)
    .catch(err => {
      error(err + " " + put_url);
    });

  }

  // Something went wrong with actions or responses
  function error(err) {
    // log as Error in console
    console.error(err);
    // append error to resultContainer
    const tr = document.createElement("tr");
    const td = document.createElement("td");
    td.innerHTML = err;
    tr.appendChild(td);
    resultContainer.appendChild(tr);
  }

</script>