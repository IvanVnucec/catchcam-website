<script>
  import GithubIcon from "$lib/icons/social/github.svg?raw";
  import XIcon from "$lib/icons/social/x.svg?raw";
  import YoutubeIcon from "$lib/icons/social/youtube.svg?raw";

  export let size = "24px";
</script>

<div class="social-icons" style="--size: {size}">
  <a href="https://github.com/commaai" target="_blank" class="github">
    {@html GithubIcon}
  </a>
  <a href="https://twitter.com/comma_ai" target="_blank" class="twitter">
    {@html XIcon}
  </a>
  <a href="https://www.youtube.com/commaai" target="_blank" class="youtube">
    {@html YoutubeIcon}
  </a>
</div>

<style>
  .social-icons {
    display: flex;
    flex-flow: row;
    align-items: center;
    justify-content: start;
    gap: 1rem;

    & svg {
      width: var(--size);
      height: var(--size);

      @media (hover: hover) and (pointer: fine) {
        &:hover {
          color: var(--color-accent);
        }
      }
      &:active {
        color: var(--color-accent);
      }
    }
  }
</style>
