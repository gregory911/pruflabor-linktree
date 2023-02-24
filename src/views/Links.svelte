<script lang="ts">
  import { link } from "svelte-routing";
  import profileImage from '../assets/profile.jpg'
  import FacebookIcon from '../assets/f_logo_RGB-Blue_1024.svg';
  import InstagramIcon from '../assets/instagram-colourful-icon.png';
  import YouTubeLogo from '../assets/yt_logo_rgb_dark.svg'
  import BandcampLogo from '../assets/bandcamp-logotype-light.svg'
  const socials = [
    { name: 'Facebook', url: 'https://www.facebook.com/pruflaborsonor/', icon: FacebookIcon},
    { name: 'Instagram', url: 'https://www.instagram.com/pruflaborsonor/', icon: InstagramIcon},
  ];
  const latestAlbums = [
    { name: 'Rude Oof Clairons', url: '/rude-oof-clairons', action_text: 'Listen', internal: true, id: 'rudeOofClairons'},
    { name: 'Harmonie', url: '/harmonie', action_text: 'Listen', internal: true, id: 'harmonie'},
    { name: 'Un Subtil Zeste de Chaos', url: '/un-subtil-zeste-de-chaos', action_text: 'Listen', internal: true, id: 'zesteChaos'}
  ];
  const accountLinks = [
    { name: 'Bandcamp', url: 'https://pruflaborsonor.bandcamp.com/music', logo: BandcampLogo, action_text: 'Shop' },
    { name: 'YouTube', url: 'https://www.youtube.com/@pruflaborsonor6707', logo: YouTubeLogo, action_text: 'Watch' }
  ];
  export let location;
</script>

<main>
    <img src="{profileImage}" alt="Pruflabor profile" class="avatar"/>
    <ul class="socials">
        {#each socials as socialLink}
            <li>
                <a href="{socialLink.url}" target="_blank" class="link">
                    <img src="{socialLink.icon}" alt="{`Icon for ${socialLink.name}`}" class="icon" />
                </a>
            </li>
        {/each}
    </ul>
    <h1>Prüflabor Sonor</h1>
    <h3>
        <span>Latest Albums</span>
        <hr/>
    </h3>
    <ul class="link-list album-list">
        {#each latestAlbums as albumLink}
            <li id="{albumLink.id}">
                {#if albumLink.internal}
                    <a use:link href="{albumLink.url}" class="link">
                        {#if (albumLink.icon)}
                            <img src="{albumLink.icon}" alt="{`Icon for ${albumLink.name}`}" class="icon" />
                        {/if}
                        <span class="text">{albumLink.name}</span>
                        <button class="style-neon">{albumLink.action_text}</button>
                    </a>
                {:else}
                    <a href={albumLink.url} target="_blank" class="link">
                        {#if (albumLink.icon)}
                            <img src="{albumLink.icon}" alt="{`Icon for ${albumLink.name}`}" class="icon" />
                        {/if}
                        {#if albumLink.logo}
                            <img src={albumLink.logo} alt={`Logo for ${albumLink.name}`} />
                        {:else }
                            <span class="text">{albumLink.name}</span>
                        {/if}
                        <button class="style-neon">{albumLink.action_text}</button>
                    </a>
                {/if}
            </li>
        {/each}
    </ul>
    <h3>
        <hr/>
    </h3>
    <ul class="link-list">
        {#each accountLinks as accountLink}
            <li>
                {#if accountLink.internal}
                    <a use:link href="{accountLink.url}" class="link">
                        {#if (accountLink.icon)}
                            <img src="{accountLink.icon}" alt="{`Icon for ${accountLink.name}`}" class="icon" />
                        {/if}
                        <span class="text">{accountLink.name}</span>
                        <button class="style-neon">{accountLink.action_text}</button>
                    </a>
                {:else}
                    <a href={accountLink.url} target="_blank" class="link">
                        {#if (accountLink.icon)}
                            <img src="{accountLink.icon}" alt="{`Icon for ${accountLink.name}`}" class="icon" />
                        {/if}
                        {#if accountLink.logo}
                            <img src={accountLink.logo} alt={`Logo for ${accountLink.name}`} />
                        {:else }
                            <span class="text">{accountLink.name}</span>
                        {/if}
                        <button class="style-neon">{accountLink.action_text}</button>
                    </a>
                {/if}
            </li>
        {/each}
    </ul>
</main>

<style>
    .socials {
        display: flex;
        flex-direction: row;
        align-items: center;
        justify-content: center;
        list-style-type: none;
        margin: 0;
        margin-top: 0.5rem;
        padding: 0;
        column-gap: 0.75rem;
    }
    .socials .link {
        display: block;
        line-height: 0.5rem;
    }
    .socials img {
        max-width: 2rem;
    }
    h3 {
        text-align: left;
        font-family: 'Oswald';
        display: flex;
        align-items: baseline;
        column-gap: 0.4rem;
    }
    h3 > hr {
        flex-grow: 2;
        border-color: #03e9f4;
        box-shadow: 0 0 5px #03e9f4, 0 0 25px #03e9f4, 0 0 50px #03e9f4, 0 0 200px #03e9f4;
        margin: 0;
    }
    .album-list .link {
        column-gap: 1.5rem;
    }
    .album-list .text {
        flex-grow: 2;
        position: relative;
        text-shadow: 1px 1px 2px #333333;
        text-align: left;
    }
    .album-list .text:before {
        content: '';
        display: block;
        background-position: center;
        background-repeat: no-repeat;
        background-size: cover;
        width: 100%;
        height: 100%;
        position: absolute;
        z-index: -1;
        top: 0;
        left: 0;
    }
    .album-list #rudeOofClairons .text {
        background-color: rgba(161,183,222,0.8);
    }
    .album-list #rudeOofClairons .text:before {
        background-image: url('/rudeOofClairons.jpg');
    }
    .album-list #harmonie .text {
        background-color: rgba(227,221,230,0.8);
    }
    .album-list #harmonie .text:before {
        background-image: url('/harmonie.jpg');
    }
    .album-list #zesteChaos .text {
        background-color: rgba(149,126,103,0.8);
    }
    .album-list #zesteChaos .text:before {
        background-image: url('/zesteChaos.jpg');
    }
    .link-list button {
        min-width: 110px;
    }

    /* Medium devices (tablets, 768px and up) */
    @media (min-width: 768px) {
        .album-list .text {
            max-width: none;
        }
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

    @media (prefers-color-scheme: light) {
        h3 > hr {
            border-color: #313f63;
            box-shadow: none;
        }
    }
</style>
