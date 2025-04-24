<script>
  import LinkButton from "$lib/components/LinkButton.svelte";
  import FeaturedCarsList from "$lib/components/FeaturedCarsList.svelte";
  import FeaturedArticles from "$lib/components/FeaturedArticles.svelte";
  import SectionHeader from "../lib/components/SectionHeader.svelte";
  import Grid from "$lib/components/Grid.svelte";
  import { vehicleCountText } from '$lib/constants/vehicles.js';

  import DeviceImage from "$lib/images/device-glow.png";
  import LaneCenteringIcon from "$lib/icons/features/lane-centering.svg?raw";
  import AdaptiveCruiseIcon from "$lib/icons/features/adaptive-cruise.svg?raw";
  import OtaUpdatesIcon from "$lib/icons/features/ota-updates.svg?raw";
  import ThreeSixtyVisionIcon from "$lib/icons/features/360-vision.svg?raw";
  import LocationIcon from "$lib/icons/features/location.svg?raw";
  import RecordingsIcon from "$lib/icons/features/recordings.svg?raw";
  import GitHubRepo from "$lib/repo-data.json";

  import RoadIcon from "$lib/icons/features/road.svg?raw";
  import SteerIcon from "$lib/icons/features/steer.svg?raw";
  import CarIcon from "$lib/icons/features/car.svg?raw";
  import PeopleIcon from "$lib/icons/features/people.svg?raw";
  import YoutubeIcon from "$lib/icons/social/youtube.svg?raw";
  import FeaturedVideos from "$lib/components/FeaturedVideos.svelte";
  import ReleaseNote from "$lib/components/ReleaseNote.svelte";
  import ProcessorIcon from "$lib/icons/features/processor.svg?raw";
  import ConnectivityIcon from "$lib/icons/features/connectivity.svg?raw";
  import DisplayIcon from "$lib/icons/features/display.svg?raw";
  import MemoryIcon from "$lib/icons/features/memory.svg?raw";
  import Space from "$lib/components/Space.svelte";

  export let data;
</script>

<svelte:head>
  <link rel="preload" as="image" href={DeviceImage[0]} />
</svelte:head>

<section class="dark" id="hero">
  <div class="container">
    <h1>catchcam</h1>
    <h2 class="muted">Speed camera detector</h2>
    <Grid columns={2} rowGap="3rem">
      <img
        src={DeviceImage}
        loading="lazy"
        alt="comma 3X device"
      />
      <div>
        <div class="mb-2">
          <Grid columns={2} columnGap="1rem" rowGap="1.25rem" size="small" wrapMode="none">
            <div class="feature-item">
              {@html LaneCenteringIcon}
              <span>Lane<br />centering</span>
            </div>
            <div class="feature-item">
              {@html RecordingsIcon}
              <span>Dashcam<br />recording</span>
            </div>
            <div class="feature-item">
              {@html AdaptiveCruiseIcon}
              <span>Adaptive<br />cruise</span>
            </div>
            <div class="feature-item">
              {@html OtaUpdatesIcon}
              <span>OTA<br />updates</span>
            </div>
            <div class="feature-item">
              {@html LocationIcon}
              <span>Lane<br />changing</span>
            </div>
            <div class="feature-item">
              {@html ThreeSixtyVisionIcon}
              <span>360° vision</span>
            </div>
          </Grid>
        </div>
        <LinkButton href="shop/comma-3x" fullWidth={true} style="accent">
          Buy now
        </LinkButton>
      </div>
    </Grid>
    <h1 class="mt-4">Buy it, plug it in, and engage.</h1>
    <h3 class="muted">
      comma 3X works with the car you already drive. It's like Tesla Autopilot
      for your Toyota, Honda, and more.
    </h3>
  </div>
</section>

<section class="light" id="compatibility">
  <div class="container">
    <h1 class="mb-7 sm-mb-3">openpilot can drive for hours without driver action.</h1>
    <Grid columns={2} rowGap="3rem">
      <h1>
        It works on {vehicleCountText} car models
        <span class="muted">from Toyota, Hyundai, Honda, and more.</span>
      </h1>
      <div>
        <FeaturedCarsList />
        <LinkButton href="/vehicles" style="primary" fullWidth={true}>
          View all {vehicleCountText} cars
        </LinkButton>
      </div>
    </Grid>
  </div>
</section>

<section class="dark" id="social">
  <div class="container">
    <SectionHeader leftLabel="comma" rightLabel="is real" />
    <h1>
      100+ million miles driven and 10k users. Our GitHub repo has
      <a href="https://github.com/commaai/openpilot" target="_blank" class="highlight">{Math.floor(GitHubRepo["stargazers_count"] / 10000) * 10}k stars</a>.
    </h1>
    <h1>
      Follow us on 𝕏
      <a href="https://twitter.com/comma_ai" target="_blank" class="highlight">@comma_ai</a>.
    </h1>
  </div>
</section>

<div id="openpilot">
  <section class="dark" id="about">
    <div class="container">
      <Grid columns={4}>
        <div class="stats-item">
          <div>{@html RoadIcon}</div>
          <span>100+ million</span>
          <span>Miles driven</span>
        </div>
        <div class="stats-item">
          <div>{@html SteerIcon}</div>
          <span>56%</span>
          <span>Miles driven are engaged</span>
        </div>
        <div class="stats-item">
          <div>{@html CarIcon}</div>
          <span>10,000+</span>
          <span>Active users</span>
        </div>
        <div class="stats-item">
          <div>{@html PeopleIcon}</div>
          <span>{Math.floor(GitHubRepo["contributors_count"] / 10) * 10}+</span>
          <span>Contributors</span>
        </div>
      </Grid>
      <div class="headline sm-mb-4">
        <h1>
          openpilot is an
          <a class="highlight" href="https://github.com/commaai/openpilot" target="_blank">open source</a>
          advanced driver assistance system that works on {vehicleCountText} car models of Toyota,
          Hyundai, Honda, and many other brands.
        </h1>
        <ul>
          <li>Automated Lane Centering</li>
          <li>Adaptive Cruise Control</li>
          <li>Lane Change Assist</li>
          <li>Driver Monitoring (no wheel nags)</li>
          <li>Can drive for hours without intervention</li>
          <li>Open source and developed on GitHub</li>
        </ul>
      </div>
      <SectionHeader leftLabel="see what it can do" rightIcon={YoutubeIcon} />
      <FeaturedVideos />
    </div>
  </section>

  <section class="light" id="benefits">
    <div class="container">
      <article>
        <hgroup>
          <p>01</p>
          <h2>Makes driving chill</h2>
        </hgroup>
        <p>
          Currently, openpilot performs the functions of Adaptive Cruise Control
          (ACC) and Automated Lane Centering (ALC). openpilot can accelerate,
          brake automatically for other vehicles, and steer to follow the
          road/lane.
        </p>
        <p>
          When openpilot is enabled, a driver monitoring system watches the driver
          and ensures the driver is attentive and ready to take over at all times.
        </p>
        <p />
        <p>
          When used correctly, these features reduce your workload as a driver,
          and can make long drives relaxing instead of tedious.
        </p>
      </article>
      <article>
        <hgroup>
          <p>02</p>
          <h2>Connects to your car</h2>
        </hgroup>
        <p>
          openpilot works by connecting to your car's CAN network. Modern cars
          accept electronic steering, gas, and brake commands to allow for ADAS
          features. openpilot can use these commands to provide much better ADAS
          features than the car manufacturers can provide.
        </p>
      </article>
      <article>
        <hgroup>
          <p>03</p>
          <h2>Modern machine learning</h2>
        </hgroup>
        <p>
          openpilot contains a state-of-the-art neural network that understands
          the road scene and predicts where to drive. This neural network has
          learned to drive by watching the millions of miles of driving data
          openpilot has recorded. This makes openpilot exceptionally good at
          nuanced situations such as driving in areas with faded lanelines,
          different countries, and more.
        </p>
      </article>
      <article>
        <hgroup>
          <p>04</p>
          <h2>Open source and community supported</h2>
        </hgroup>
        <p>
          openpilot is developed by comma and by users like you. We welcome both
          pull requests and issues on
          <a class="highlight" href="http://github.com/commaai/openpilot" target="_blank">GitHub</a>.
          Bug fixes and new car ports are strongly encouraged. Check out the
          <a class="highlight" href="https://github.com/commaai/openpilot/blob/master/docs/CONTRIBUTING.md" target="_blank">contributing docs</a>.
        </p>
        <LinkButton href="https://github.com/commaai/openpilot">
          View on GitHub
        </LinkButton>
        <div class="release-notes">
          <h3>Latest Release Notes</h3>
          {#each data.releaseNotes as release}
            <ReleaseNote releaseNote={release} />
          {/each}
        </div>
      </article>
      <article>
        <hgroup>
          <p>05</p>
          <h2>Try openpilot on the comma <span style="text-transform: none;">3X</span></h2>
        </hgroup>
        <p>
          Love it or return it. Every comma 3X comes with a 30-day money back
          trial.
        </p>
        <Grid columns={2} alignItems="center">
          <img src={DeviceImage} loading="lazy" alt="comma 3X device" />
          <div>
            <Grid columns={2}>
              <div class="feature-item">
                <div>{@html ThreeSixtyVisionIcon}</div>
                <span>360° vision<br />W/ 3 cameras</span>
              </div>
              <div class="feature-item">
                <div>{@html ProcessorIcon}</div>
                <span>Qualcomm snapdragon 845</span>
              </div>
              <div class="feature-item">
                <div>{@html ConnectivityIcon}</div>
                <span>LTE & WiFi</span>
              </div>
              <div class="feature-item">
                <div>{@html DisplayIcon}</div>
                <span>6" BEAUTIFUL<br />OLED display</span>
              </div>
              <div class="feature-item">
                <div>{@html MemoryIcon}</div>
                <span>CAN FD ENABLED</span>
              </div>
              <div class="feature-item">
                <div>{@html LocationIcon}</div>
                <span>High-precision GPS</span>
              </div>
            </Grid>
            <Space multiplier={3} />
            <LinkButton href="shop/comma-3x" fullWidth={true} style="primary">
              Buy now
            </LinkButton>
          </div>
        </Grid>
      </article>
      <article>
        <hgroup>
          <p>06</p>
          <h2>Proven on the road</h2>
        </hgroup>
        <p>
          Our 10,000+ users have driven over 100+ million miles with a device
          running openpilot. Over 56% of those miles were driven by openpilot,
          with the driver supervising.
        </p>
      </article>
    </div>
  </section>
</div>

<style>
  #hero {
    & .feature-item {
      align-items: center;
      display: flex;
      color: white;

      & img {
        border: 1px solid #000;
        width: 52px;
        margin-right: 0.5rem;
        padding: 0.375rem;
        display: inline-block;
      }

      & span {
        color: var(--color-muted);
        text-transform: uppercase;
        flex: 1;
        font-family: JetBrains Mono, monospace;
        font-size: 1rem;
        font-weight: 400;
        line-height: 1.25;
        margin-left: 1rem;
      }
    }

    & h3 {
      line-height: 1.4;
    }

    @media screen and (max-width: 375px) {
      & .feature-item span {
        font-size: 0.75rem;
      }
    }
  }

  #openpilot {
    & .stats-item {
      display: flex;
      align-items: flex-start;
      flex-flow: column;
      color: white;

      & span:first-of-type {
        margin-top: 0.5rem;
        margin-bottom: 0.25rem;
        font-size: 2rem;
        font-weight: 600;
      }

      & span:last-of-type {
        color: var(--color-muted);
        text-transform: uppercase;
        font-family: JetBrains Mono, monospace;
        font-size: 1rem;
        font-weight: 400;
      }

      @media screen and (max-width: 1024px) {
        & span:first-of-type {
          font-size: 1.5rem;
        }

        & span:last-of-type {
          font-size: 0.875rem;
        }
      }
    }

    & .feature-item {
      display: flex;
      align-items: center;
      flex-flow: row;

      & div {
        border: 1px solid #000;
        width: 48px;
        padding: 0.375rem;
        display: inline-block;
        color: black;
      }

      & span {
        color: var(--color-muted);
        text-transform: uppercase;
        font-family: JetBrains Mono, monospace;
        font-size: 1rem;
        font-weight: 400;
        margin-left: 1rem;
      }
    }

    & .headline {
      margin-top: 4rem;
      margin-bottom: 6rem;

      & h1 {
        font-size: 2.5rem;
        line-height: 1.2;
      }

      & ul {
        padding-left: 0;
        list-style: none;

        & li {
          margin-bottom: 0.5rem;
          padding-left: 2rem;
          background: url("$lib/icons/ui/checkmark.svg?raw") left center no-repeat;
        }
      }

      @media screen and (max-width: 512px) {
        & h1 {
          font-size: 2rem;
        }

        & ul {
          padding-top: 1rem;

          & li {
            font-size: 1.25rem;
          }
        }
      }
    }

    & article {
      margin-bottom: 6rem;

      & hgroup {
        & p {
          opacity: 0.5;
          font-family: JetBrains Mono, monospace;
          margin: 0 0 0.5rem;
          font-size: 1.5rem;
        }

        & h2 {
          font-weight: 600;
          font-size: 2.5rem;
          text-transform: lowercase;
          line-height: 1.2;
          margin-bottom: 1rem;
        }
      }

      & p {
        font-size: 1.5rem;
      }

      & h3 {
        margin-top: 4rem;
        margin-bottom: 1rem;
      }

      @media screen and (max-width: 512px) {
        margin-bottom: 4rem;

        & hgroup {
          & h2 {
            font-size: 2rem;
          }
        }

        & p {
          font-size: 1.25rem;
        }

        & .release-notes {
          width: 100%;
        }
      }
    }

    & .release-notes {
      width: 80%;
    }
  }
</style>
