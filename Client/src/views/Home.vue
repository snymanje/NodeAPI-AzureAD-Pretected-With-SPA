<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png">
    <p>{{ data }}</p>
    <p>{{ profile }}</p>
  </div>
</template>

<script>
import axios from "axios";
// @ is an alias to /src
import HelloWorld from "@/components/HelloWorld.vue";

export default {
  name: "home",
  components: {
    HelloWorld
  },
  data() {
    return {
      data: "This should come from azure function",
      profile: null
    };
  },
  created() {
    axios
      .get(
        "https://js-helloworld-demo.azurewebsites.net/api/HelloWorld?name=%22sdfsdf%22",
        {
          headers: {
            Authorization:
              "Bearer eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiIsIng1dCI6IkhCeGw5bUFlNmd4YXZDa2NvT1UyVEhzRE5hMCIsImtpZCI6IkhCeGw5bUFlNmd4YXZDa2NvT1UyVEhzRE5hMCJ9.eyJhdWQiOiIyMzBiZGQ5NC04OTkwLTRhOTQtYjUxZi00MjU3MGYxYTA3MzAiLCJpc3MiOiJodHRwczovL3N0cy53aW5kb3dzLm5ldC9jM2ZhYjVkMy0yMTAyLTRjNGItYWYyZS0wNTNhMDMxMTcyNTcvIiwiaWF0IjoxNTU4NDU1NTIxLCJuYmYiOjE1NTg0NTU1MjEsImV4cCI6MTU1ODQ1OTQyMSwiYWlvIjoiNDJaZ1lLaGRvZXArOTFqQTQyVXhUYmxPQWFwbXlub2RiTFZibGpBSC9lQXR0Z3l1Zmd3QSIsImFtciI6WyJwd2QiXSwiZmFtaWx5X25hbWUiOiJTbnltYW4iLCJnaXZlbl9uYW1lIjoiSmVhbiIsImlwYWRkciI6IjEwNS4xOS40OC41MSIsIm5hbWUiOiJKZWFuIFNueW1hbiIsIm5vbmNlIjoiMDdmMDAzYmMtOGEwZS00YjI5LThjNGEtNWQxOTc3NDBlZmY1Iiwib2lkIjoiZjlkNGIyYTItODc1OC00YmNhLTk2NGUtM2I3OTIyYzc5ZjFmIiwib25wcmVtX3NpZCI6IlMtMS01LTIxLTExNzcyMzg5MTUtNTE1OTY3ODk5LTY4MjAwMzMzMC01MjgxOCIsInN1YiI6ImIyekhkOWZtMHd0aXFYLVlDRUgtR21RVWdZa3U1bXhDazg4OTdPNnF6WWsiLCJ0aWQiOiJjM2ZhYjVkMy0yMTAyLTRjNGItYWYyZS0wNTNhMDMxMTcyNTciLCJ1bmlxdWVfbmFtZSI6IkplYW5TbkB0ZmcuY28uemEiLCJ1cG4iOiJKZWFuU25AdGZnLmNvLnphIiwidXRpIjoiWEVTOUlna0tmRTJoZUFoT2h2OGpBQSIsInZlciI6IjEuMCJ9.FuhMF4nw3Gz2exx_VV2dL4WPndupv01JDbkOzRSaX1hUXyFuMlpVsns4cTTr96yLA37omh6wAg7sxIYYYJu7_Xh1MvufEC6PHLHt-oD5zkz-86RuTt51vXxu4nmZI1la9qhhPSC_Mwvfh2yR0IzxAroF1wOBqLyH9IeD-BnqstGGJmneTae63n0AhH0QiLJ6KCwwdgGzQlxsQ34quUI7lepAuOEnuhhZAhjUjSmNPckQfjrHgfW9o1fOoE55RTqWZe0fPmnMkXBe42lTp_apCvjLwngqUEFb130Lt_APRwOD5y3BSSoZxFCG0S7Z4MGFsXpB9_H4Iwia7xJDjFe8ew"
          }
        }
      )

      .then(res => {
        console.log(res.data);
        this.data = res.data;
      })
      .catch(error => {
        console.log(error);
      });
  }
};
</script>
