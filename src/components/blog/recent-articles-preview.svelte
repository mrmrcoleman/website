<script lang="ts">
  import type { BlogPost } from "../../types/blog-post.type";

  import { page, session } from "$app/stores";
  import MoreArticles from "../more-articles.svelte";

  const recentPosts = $session.posts.slice(0, 4);
  $: recentPostsWithoutCurrent = recentPosts
    .filter((post: BlogPost) => $page.path.indexOf(post.slug) === -1)
    .slice(0, 3);
</script>

<MoreArticles posts={recentPostsWithoutCurrent} />
