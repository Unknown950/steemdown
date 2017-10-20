 
<html>
<head><title>Alternative posting page when SteemIt is down</title></head>
<body>
<h2>Post an article on SteemIt when SteemIt is down!</h2><br/>
<h2>Recently SteemIt had a couple of issues and some days it was just completly down. Here is an alternative to post your articles.</h2>
<h2>Just enter your username, your posting key, the title of your post and your actual post.<br>
Once you are done press the "Submit" button and your post will appear on the steemit blockchain.</h2>
<br>
Username: <input id="username" type="text"><br/>
Posting key: <input id="postingKey" type="password" size="65"><br/>
Title of article: <input id="title" type="text"><br/>
Article text:<br/>
<textarea id="article"></textarea><br/>
<input id="postIt" type="button" value="Post it!" onClick=postArticle()>
 
</body>
</html>

<script src="https://cdn.steemjs.com/lib/latest/steem.min.js"></script>

<script language="JavaScript">
function postArticle()
{
  steem.broadcast.comment(
    document.getElementById('postingKey').value, // posting wif
    '', // author, leave blank for new post
    'steemtest', // first tag
    document.getElementById('username').value, // username
    'name-of-my-test-article-post', // permlink
    document.getElementById('title').value, // Title
    document.getElementById('article').value, // Body of post
    // json metadata (additional tags, app name, etc)
    { tags: ['secondtag'], app: 'steemjs-test!' },
    function (err, result) {
      if (err)
        alert('Failure! ' + err);
      else
        alert('Success!');
    }
  );
}
</script>
