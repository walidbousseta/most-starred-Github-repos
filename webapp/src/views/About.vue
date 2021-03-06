<template>
  <div class="about">
    <h1>About the project</h1>
    <h2>Idea of the App</h2>
    <p>
      The task is to implement a small webapp that will list the most starred
      Github repos that were created in the last 30 days. You'll be fetching the
      sorted JSON data directly from the Github API (Github API explained down
      below).
    </p>
    <h2>Features</h2>
    <ul>
      <li
        >As a User I should be able to list the most starred Github repos that
        were created in the last 30 days.
      </li>
      <li
        >As a User I should see the results as a list. One repository per
        row.</li
      >
      <li>
        As a User I should be able to see for each repo/row the following
        detalis :
        <ul>
          <li>Repository name</li>
          <li>Repository description</li>
          <li>Number of stars for the repo.</li>
          <li>Number of issues for the repo.</li>
          <li>Username and avatar of the owner.</li>
        </ul>
      </li>
      <li
        >As a User I should be able to keep scrolling and new results should
        appear (pagination).</li
      >
    </ul>
    <h2>Mockups</h2>
    <img src="@/assets/mockup.png" alt="mockup"> <br>
    <img src="@/assets/row_explained.png" alt="mockup"> 

    <br><hr>
    <h1 style="margin-top: 50px;">About me</h1>
    <ul>
      <li><label>Name</label>    : Walid BOUSSETA</li>
      <li><label>Title</label>  : Data Scientist at SiliconeSignal Technologies | Researcher PhD Student at ESTM</li>
      <li><label>Email</label>  : walid.bousseta@gmail.com </li>
      <li><label>Portfilio</label> : <a href="https://www.bousseta.ml/">bousseta.ml</a></li>
    </ul>
  </div>
</template>
<style scoped>
.about{
  margin: 50px auto;
  width: 70%;
}
img{
  width: 100%;
  height: 50%;
  margin: 10px 15px;
}

</style>