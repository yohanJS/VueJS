new Vue({
  el: '#GetBlogs',
  data () {
    return {
      info: null
    }
  },
  mounted () {
    axios
      .get('https://localhost:7011/BlogPost')
        .then((response) => {
          // Display the response in the console
          console.log(response);

          // Set the response data to the component's data property
          this.info = response.data;
        })
        .catch((error) => {
          // Handle errors
          console.error('Error fetching data:', error);
        });
  }
})