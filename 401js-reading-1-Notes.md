# **Reading Assignment 1 - Node Ecosystem, TDD, CI/CD**

  ## Describe (in plain English) what Array.map() does
    + Array.map() takes whatever function is declared as a parameter in the .map() method and applies it to each index in the array, then creates a new array of the same length containing the results. This does not modify the original array used.
  ## Describe (in plain English) what Array.reduce() does
    + Runs a callback function that receives (accumulator, value, index) as parameters for each value in the array, then returns whatever value you'd like using the accumulator. This does not modify the original array either.
  ## Provide code snippets showing how to use superagent() to fetch data from a URL and log the result
    + With normal Promise .then() syntax
      `let info;`
      `let API = process.env.API;`

      `let URL = `https://www.api.com/api/json/${searchedInfo}?key=${API}`;`

      `const apiCall = superagent.get(URL).then(data => {`

        `info = data.body[0].meta ? data.body[0].meta.info : ['Not Found'];`

        `return info;`

      `});`

console.log(info);

    + Again with async / await syntax
async function fetchData(){     

     let API = process.env.API;

     let URL = `https://www.api.com/api/json/${searchedInfo}?key=${API}`;

     const response = await superagent.get(URL);

     console.log(response);

}

  ## Explain promises as though you were mentoring a Code 301 level student
A promise is an object that will produce some type of value after some time. This usually is in the form of calls to a server for information. Either the requested info will be returned, or a reason why the value couldn't be returned.
  ## Are all callback functions considered to be Asynchronous? Why or Why Not?
No, many callback functions, such as the .foreach() method, will not continue to the next iteration until the previous is complete.
