<!-- App.svelte -->
<script>
  const links = [
    { name: 'Bandcamp', url: 'https://pruflabor.bandcamp.com/', logo: 'bandcamp.png' },
    { name: 'Apple Music', url: 'https://music.apple.com/us/artist/pruflabor/1479360306', logo: 'apple_music.png' },
    { name: 'Spotify', url: 'https://open.spotify.com/artist/6HgwKljKxeqBZFvudJzQI7', logo: 'spotify.png' },
    { name: 'Amazon Music', url: 'https://www.amazon.com/Pruflabor/e/B07KJK9FLV', logo: 'amazon_music.png' },
    { name: 'YouTube', url: 'https://www.youtube.com/channel/UCg_BX-kKjPYHWFLVHYBhLQQ', logo: 'youtube.png' }
  ];
</script>

<h1>Pruflabor Music Accounts</h1>
<ul>
  {#each links as link}
    <li>
      <a href={link.url} target="_blank">
        <img src={link.logo} alt={`Logo for ${link.name}`} />
        {link.name}
      </a>
    </li>
  {/each}
</ul>
