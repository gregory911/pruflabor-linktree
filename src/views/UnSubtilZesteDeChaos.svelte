<script lang="ts">
  import BandcampLogo from '../assets/bandcamp-logotype-light.svg'
  import AppleMusicLogo from '../assets/US-UK_Apple_Music_Listen_on_Lockup_RGB_wht_072720.svg'
  import SpotifyLogo from '../assets/Spotify_Logo_RGB_Green.svg'
  import AmazonMusicLogo from '../assets/am4a-logo_mod.svg'
  import YouTubeMusicLogo from '../assets/yt_music_full_rgb_white.svg'
  import TidalLogo from '../assets/tidal-horizontal-white-rgb.svg'
  const links = [
    { name: 'Bandcamp', url: 'https://pruflaborsonor.bandcamp.com/album/un-subtil-zeste-de-chaos', logo: BandcampLogo },
    { name: 'Apple Music', url: 'https://music.apple.com/us/album/un-subtil-zeste-de-chaos/1608285042', logo: AppleMusicLogo },
    { name: 'Spotify', url: 'https://open.spotify.com/album/1Xk60FiVplIMahYkAFQraG?si=10PIEB9mS3qUOC7Jf2Qk7g', logo: SpotifyLogo },
    { name: 'YouTube Music', url: 'https://music.youtube.com/playlist?list=OLAK5uy_mq6CWRMnZubtXq1CjZY21TiGP8Ftjt310&feature=share', logo: YouTubeMusicLogo },
    { name: 'Amazon Music', url: 'https://music.amazon.ca/albums/B09RQ9WJ6B', logo: AmazonMusicLogo },
    { name: 'Tidal', url: 'https://tidal.com/browse/album/215058030', logo: TidalLogo }
  ];
</script>

<main>
    <a href="/"><h1>Prüflabor Sonor</h1></a>
    <iframe class="deezer-player" title="deezer-widget" src="https://widget.deezer.com/widget/dark/album/292615012" width="100%" height="300" frameborder="0" allowtransparency="true" allow="encrypted-media; clipboard-write"></iframe>
    <ul class="link-list">
        {#each links as link}
            <li>
                <a href={link.url} target="_blank" class="link" rel="noreferrer">
                    <img src={link.logo} alt={`Logo for ${link.name}`} />
                    <button class="style-neon">Play</button>
                </a>
            </li>
        {/each}
    </ul>
</main>

<style>
    iframe.deezer-player {
        border-radius: 10px;
    }

    /* Medium devices (tablets, 768px and up) */
    @media (min-width: 768px) {
    }

    /* Large devices (desktops, 992px and up) */
    @media (min-width: 992px) {
    }

    /* X-Large devices (large desktops, 1200px and up) */
    @media (min-width: 1200px) {
    }

    /* XX-Large devices (larger desktops, 1400px and up) */
    @media (min-width: 1400px) {
    }
</style>
