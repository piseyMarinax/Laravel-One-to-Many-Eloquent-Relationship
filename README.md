# Laravel-One-to-Many-Eloquent-Relationship

+ Retrieve Records:

$post = Post::find(1);
$comments = $post->comments;
dd($comments);

$comment = Comment::find(1); 
$post = $comment->post;
dd($post);

--------------------------------------------------------

+ Create Records:

$post = Post::find(1);
$comment = new Comment;
$comment->comment = "Hi ItSolutionStuff.com";
$post = $post->comments()->save($comment);

$post = Post::find(1);
 
$comment1 = new Comment;
$comment1->comment = "Hi ItSolutionStuff.com Comment 1";
$comment2 = new Comment;
$comment2->comment = "Hi ItSolutionStuff.com Comment 2";
$post = $post->comments()->saveMany([$comment1, $comment2]);

--------------------------------------------------------

+ Update Records:

$comment = Comment::find(1);
$post = Post::find(2);
$comment->post()->associate($post)->save();
