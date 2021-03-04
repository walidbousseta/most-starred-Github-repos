<template>
  <div class="container">
    <img :src="owner.avatar_url" :alt="id" />
    <div class="info">
      <h1>{{ name }}</h1>
      <p>{{ description }}</p>
      <div class="subinfo">
        <span class="sep"><b>Likes:</b> {{ watchers_count }}</span>
        <span class="sep"><b>Views:</b> {{ open_issues_count }}</span>
        <span>Submitted {{ getTimeInterval(created_at) }} days ago by {{owner.login}}</span>
      </div>
    </div>
  </div>
</template>


<script>
export default {
  name: "Card",
  methods: {
    getTimeInterval(created_date) {
      // The number of milliseconds in one day
      const ONE_DAY = 1000 * 60 * 60 * 24;

      // Calculate the difference in milliseconds
      const differenceMs = Math.abs(new Date() - new Date(created_date));

      // Convert back to days and return
      return Math.round(differenceMs / ONE_DAY);
    },
  },
  props: {
    id: Number,
    node_id: String,
    name: String,
    full_name: String,
    private: Boolean,
    owner: Object,
    html_url: String,
    description: String,
    fork: Boolean,
    url: String,
    forks_url: String,
    keys_url: String,
    collaborators_url: String,
    teams_url: String,
    hooks_url: String,
    issue_events_url: String,
    events_url: String,
    assignees_url: String,
    branches_url: String,
    tags_url: String,
    blobs_url: String,
    git_tags_url: String,
    git_refs_url: String,
    trees_url: String,
    statuses_url: String,
    languages_url: String,
    stargazers_url: String,
    contributors_url: String,
    subscribers_url: String,
    subscription_url: String,
    commits_url: String,
    git_commits_url: String,
    comments_url: String,
    issue_comment_url: String,
    contents_url: String,
    compare_url: String,
    merges_url: String,
    archive_url: String,
    downloads_url: String,
    issues_url: String,
    pulls_url: String,
    milestones_url: String,
    notifications_url: String,
    labels_url: String,
    releases_url: String,
    deployments_url: String,
    created_at: String,
    updated_at: String,
    pushed_at: String,
    git_url: String,
    ssh_url: String,
    clone_url: String,
    svn_url: String,
    homepage: String,
    size: Number,
    stargazers_count: Number,
    watchers_count: Number,
    language: String,
    has_issues: Boolean,
    has_projects: Boolean,
    has_downloads: Boolean,
    has_wiki: Boolean,
    has_pages: Boolean,
    forks_count: Number,
    mirror_url: String,
    archived: Boolean,
    disabled: Boolean,
    open_issues_count: Number,
    license: Object,
    forks: Number,
    open_issues: Number,
    watchers: Number,
    default_branch: String,
    score: Number,
  },
};
</script>

<style>
.cards {
  display: block;
  width: 700px;
  margin: 0px auto;
}
.container {
  width: 700px;
  max-height: 200px;
  overflow: hidden;
  border-radius: 10px;
  -webkit-box-shadow: 4px 4px 10px 1px rgba(0, 0, 0, 0.31);
  -moz-box-shadow: 4px 4px 10px 1px rgba(0, 0, 0, 0.31);
  box-shadow: 4px 4px 10px 1px rgba(0, 0, 0, 0.31);
  margin: 50px auto;
  position: relative;
}

img {
  width: 180px;
  height: 200px;
  background-repeat: no-repeat;
  background-size: cover;
  padding-right: 10px;
  float: left;
}

.info {
  margin: 0px;
  padding: 0px;
}

.subinfo {
  border-top: 1px solid #ababab;
  padding-top: 8px;
  padding-bottom: 8px;
  text-align: start;
  position: absolute;
  bottom: 0px;
  width: 100%;
  left: 180px;
}

span {
  padding: 0px 10px;
}

p,
h1 {
  margin: 10px;
  padding: 0px;
}

p {
  text-indent: 5%;
  overflow: hidden;
  text-overflow: ellipsis;
  display: -webkit-box;
  -webkit-line-clamp: 5; /* number of lines to show */
  -webkit-box-orient: vertical;
}

.sep {
  border-right: 1px solid #ababab;
}
</style>