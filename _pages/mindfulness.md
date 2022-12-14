---
layout: navbar
title: Mental Health News Articles 
permalink: /api/
---

<h1>Copy and Paste the URLs into a new tab to view the articles.</h1>
<!-- HTML table fragment for page -->
<table>
  <thead>
  <tr>
    <th>Quote</th>
    <th>Author</th>
    <th>Category</th>
  </tr>
  </thead>
  <tbody 
  id="result">
    <!-- javascript generated data -->
  </tbody>
</table>

<!-- Script is layed out in a sequence (no function) and will execute when page is loaded -->
<script>
  // prepare HTML result container for new output
  const resultContainer = document.getElementById("result");

// prepare fetch options
const options = {
	method: 'GET',
	headers: {
		'X-RapidAPI-Key': 'a8ea413753msh15f71679011b0bbp19bf3ejsn899c6392170a',
		'X-RapidAPI-Host': 'metaapi-mindfulness-quotes.p.rapidapi.com'
	}
};

fetch('https://metaapi-mindfulness-quotes.p.rapidapi.com/v1/mindfulness', options)
fetch(url, options)
    // response is a RESTful "promise" on any successful fetch
    .then(response => {
      // check for response errors
      if (response.status !== 200) {
          const errorMsg = 'Database response error: ' + response.status;
          console.log(errorMsg);
          const tr = document.createElement("tr");
          const td = document.createElement("td");
          td.innerHTML = errorMsg;
          tr.appendChild(td);
          resultContainer.appendChild(tr);
          return;
      }
      // valid response will have json data
      response.json().then(data => {
          console.log(data);
          for (const row of data) {
            // tr and td build out for each row
            const tr = document.createElement("tr");
            const quote = document.createElement("td");
            const author = document.createElement("td");
            const category = document.createElement("td");
            // data is specific to the API
            quote.innerHTML = row.quote; 
            author.innerHTML = row.author;
            category.innerHTML = row.category; 
            // this build td's into tr
            tr.appendChild(quote);
            tr.appendChild(author);
            tr.appendChild(category);
            // add HTML to container
            resultContainer.appendChild(tr);
          }
      })
  })
  // catch fetch errors (ie ACCESS to server blocked)
  .catch(err => {
    console.error(err);
    const tr = document.createElement("tr");
    const td = document.createElement("td");
    td.innerHTML = err;
    tr.appendChild(td);
    resultContainer.appendChild(tr);
  });
</script>
