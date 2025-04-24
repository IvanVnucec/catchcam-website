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

  import DeviceVideoWebm from "$lib/videos/comma-3x.webm";
  import DeviceVideoMp4 from "$lib/videos/comma-3x.mp4";
  import Comma3XProductImage from "$lib/images/products/comma-3x/comma-3x-promo.jpg";
  import OBDCCableImage from "$lib/images/products/obd-c-cable/obd-c-right-cable.jpg";
  import ReplacementMountsImage from "$lib/images/products/replacement-mounts/replacement-mounts-3x.png";
  import MoonIcon from "$lib/icons/features/moon.svg?raw";
  import CableIcon from "$lib/icons/features/cable.svg?raw";
  import SetupGuide from "$lib/components/SetupGuide.svelte";
  import Comma3XImage from "$lib/images/device.png";
  import CarBrandCollageImage from "$lib/images/car-brand-collage.jpg";
  import Comma3XGlowImage from "$lib/images/device-glow.png";

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

<div id="shop">
  <div class="hero">
    <video autoplay muted loop webkit-playsinline playsinline disableRemotePlayback>
      <source src={DeviceVideoWebm} type="video/webm" />
      <source src={DeviceVideoMp4} type="video/mp4" />
    </video>
    <hgroup>
      <h1>comma 3X</h1>
      <h2>Make driving chill</h2>
    </hgroup>
  </div>
  <slot />

  <section class="light" id="description">
    <div class="container">
      <Grid rowGap="0" templateColumns="0.5fr 1.25fr">
        <h2>Meet the comma 3X</h2>
        <div class="description">
          <p>
            The comma 3X is custom hardware designed to live in your car, and purpose built to run openpilot. The comma 3X has three beautiful HDR cameras, two cameras to watch the road and one night-vision camera to see inside the car.
          </p>
          <p>
            Besides cameras, the comma 3X has a suite of connectivity and sensors including cellular LTE, Wi-Fi, an IMU, high-precision GPS, and microphones.
          </p>
        </div>
      </Grid>
      <div class="mobile-hero">
        <video autoplay muted loop webkit-playsinline playsinline disableRemotePlayback>
          <source src={DeviceVideoWebm} type="video/webm" />
          <source src={DeviceVideoMp4} type="video/mp4" />
        </video>
        <hgroup>
          <h1>comma 3X</h1>
          <h2>Make driving chill</h2>
        </hgroup>
      </div>
      <hr />
      <Grid rowGap="0" templateColumns="0.5fr 1.25fr">
        <h2>In the Box</h2>
        <div class="box-contents">
          <div>
            <img src={Comma3XProductImage} loading="lazy" alt="comma 3X device">
            <p>comma 3X</p>
          </div>
          <div>
            <img src={OBDCCableImage} loading="lazy" alt="1.5ft right-angle OBD-C cable">
            <p>1.5 ft right-angle OBD-C cable</p>
          </div>
          <div>
            <img src={ReplacementMountsImage} loading="lazy" alt="mount">
            <p>2 standard mounts (some cars ship with 8 degree mounts. Details
              <a
                href="https://github.com/commaai/openpilot/blob/master/docs/CARS.md#supported-cars"
                target="_blank" class="highlight">here</a
              >.)
            </p>
          </div>
        </div>
      </Grid>
      <hr />
      <Grid rowGap="0" templateColumns="0.5fr 1.25fr">
        <h2>On-device Storage</h2>
        <div>
          <p>comma 3X includes on-board storage to store your drives.</p>
          <div class="spec-card">
            <div class="header">
              <div>{@html MemoryIcon}</div>
              <span>Storage</span>
            </div>
            <div class="contents">
              <hgroup>
                <strong>128<span class="unit">GB</span></strong>
                <span>built in storage</span>
              </hgroup>
              <div>~4.5 hours of footage</div>
            </div>
          </div>
          <p>
            Want your video footage saved for longer? – Sign up for <a href="/connect" class="highlight">comma prime</a> for 1 year of cloud video storage.
          </p>
          <p>
            comma 3X includes one free month of comma prime.
            To claim your free prime trial, log into <a href="https://connect.comma.ai/" target="_blank" class="highlight">comma connect</a>.
            Once paired, you can see your recorded drives, SSH into your device from anywhere, and more.
          </p>
        </div>
      </Grid>
      <hr />
      <Grid rowGap="0" templateColumns="0.5fr 1.25fr">
        <h2>Tech Specs</h2>
        <div>
          <div class="spec-card">
            <div class="header">
              <div>{@html ThreeSixtyVisionIcon}</div>
              <span>Cameras</span>
            </div>
            <div class="contents">
              Three 1080p cameras w/ 140 dB of dynamic range: dual-cam 360° vision and a narrow cam to see far-away objects
            </div>
          </div>
          <div class="spec-card">
            <div class="header">
              <div>{@html ProcessorIcon}</div>
              <span>Processor</span>
            </div>
            <div class="contents">
              Qualcomm Snapdragon 845
            </div>
          </div>
          <div class="spec-card">
            <div class="header">
              <div>{@html MemoryIcon}</div>
              <span>Can FD Enabled</span>
            </div>
            <div class="contents">
              Supports CAN FD vehicles without extra hardware
            </div>
          </div>
          <div class="spec-card">
            <div class="header">
              <div>{@html MemoryIcon}</div>
              <span>Storage</span>
            </div>
            <div class="contents">
              128GB built in storage
            </div>
          </div>
          <div class="spec-card">
            <div class="header">
              <div>{@html ConnectivityIcon}</div>
              <span>Connectivity</span>
            </div>
            <div class="contents">
              <ul>
                <li>LTE</li>
                <li>Wi-Fi</li>
                <li>High-Precision GPS</li>
              </ul>
            </div>
          </div>
          <div class="spec-card">
            <div class="header">
              <div>{@html MoonIcon}</div>
              <span>Night-Vision</span>
            </div>
            <div class="contents">
              IR LEDs for interior night-vision monitoring
            </div>
          </div>
          <div class="spec-card">
            <div class="header">
              <div>{@html DisplayIcon}</div>
              <span>Display</span>
            </div>
            <div class="contents">
              2160x1080 Beautiful OLED display
            </div>
          </div>
          <div class="spec-card">
            <div class="header">
              <div>{@html CableIcon}</div>
              <span>Ports</span>
            </div>
            <div class="contents">
              <ul>
                <li>OBD-C port (USB-C w/ CAN)</li>
                <li>USB 3.1 Gen 2 port</li>
              </ul>
            </div>
          </div>
        </div>
      </Grid>
      <hr />
      <SetupGuide
        productName="comma 3X"
        title="Setup Guide"
        stepCount={7}
        estimatedMinutes={15}
        link="/setup"
        image={Comma3XImage}
      />
    </div>
  </section>

  <section class="dark" id="compatibility">
    <div class="container">
      <div class="compatibility">
        <Grid>
          <div>
            <hgroup>
              <span>Car harness</span>
              <h2>comma 3X is compatible with {vehicleCountText} cars</h2>
            </hgroup>
            <p>
              A supported vehicle is one that just works when you install a comma device.
              All supported cars provide a better experience than any stock system.
            </p>
            <LinkButton href="/vehicles" style="secondary" fullWidth={false}>View all {vehicleCountText} cars</LinkButton>
          </div>
          <img src={CarBrandCollageImage} loading="lazy" alt="collage of some supported car brands" />
        </Grid>
      </div>
      <div class="compatibility">
        <Grid>
          <img src={Comma3XGlowImage} loading="lazy" alt="comma 3X device" />
          <div>
            <hgroup>
              <span>Software</span>
              <h2>Works with openpilot</h2>
            </hgroup>
            <p>
              comma 3X ships without software installed, so you need to install software.
              It is compatible with <a href="/openpilot" class="highlight">openpilot</a> and works with a wide variety of community supported forks.
            </p>
            <LinkButton href="/openpilot" style="secondary" fullWidth={false}>Openpilot</LinkButton>
          </div>
        </Grid>
      </div>
      <h2 class="guarantee">
        Try our 30-day money-back trial and see why 92% of buyers keep their comma 3X and why Consumer Reports rated us as the
        <a href="https://data.consumerreports.org/wp-content/uploads/2020/11/consumer-reports-active-driving-assistance-systems-november-16-2020.pdf" class="highlight">top ADAS system.</a>
      </h2>
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

  #shop {
    & h2 {
      font-size: 1.875rem;
      font-weight: 600;
    }

    & p {
      font-size: 1.25rem;
    }

    & hr {
      margin: 3rem 0;
    }

    & #description {
      & .description {
        & p:first-of-type {
          margin-top: 0;
        }

        & p:last-of-type {
          margin-bottom: 0;
        }
      }

      @media screen and (max-width: 1024px) {
        & {
          margin-bottom: 3rem;
        }
      }

      & .box-contents {
        display: flex;
        flex-wrap: wrap;
        text-align: center;

        & > div {
          width: 300px;
          margin-bottom: 2rem;

          & img {
            max-height: 150px;
          }

          & p {
            margin: 0 2rem;
          }
        }
      }

      & .spec-card {
        border: 1px solid #000;
        margin-bottom: 1.5rem;

        & .header {
          display: flex;
          align-items: center;
          border-bottom: 1px solid #000;

          & div {
            display: flex;
            align-items: center;
            justify-content: center;
            background-color: black;
            color: white;
            width: 48px;
            height: 48px;

            & svg {
              width: 36px;
              height: 36px;
              color: white;
            }
          }

          & span {
            font-family: JetBrains Mono, monospace;
            font-size: 0.875rem;
            font-weight: 400;
            text-transform: uppercase;
            margin-left: 1rem;
          }
        }

        & .contents {
          display: flex;
          align-items: center;
          justify-content: space-between;
          padding: 0.875rem 1rem;

          & hgroup {
            & strong {
              display: block;
              font-size: 1.25rem;
              font-weight: 600;
            }

            & .unit {
              font-size: 0.875rem;
              text-transform: uppercase;
            }
          }

          & li {
            font-size: 1rem;
          }
        }
      }
    }

    & hgroup {
      & span {
        font-family: JetBrains Mono, monospace;
        font-size: 1rem;
        margin-bottom: 0.5rem;
      }

      & h2 {
        font-size: 2.5rem;
        font-weight: 600;
        line-height: 1.2;
      }
    }

    & .compatibility {
      margin-bottom: 5rem;

      @media screen and (max-width: 768px) {
        & {
          margin-bottom: 5rem;
        }
      }

      & hgroup {
        & h2 {
          text-wrap: balance;
        }

        & span {
          text-transform: uppercase;
        }
      }

      & p, & p > a {
        color: white;
      }
    }

    & .guarantee {
      font-size: 3rem;
      line-height: 1.25;

      & a {
        color: white;
      }
    }

    & .mobile-hero {
      display: none;
      position: relative;
      color: white;

      & hgroup {
        position: absolute;
        top: 50%;
        left: 50%;
        transform: translate(-50%, -50%);
        width: 100%;

        text-align: center;
        text-transform: uppercase;

        & h1 {
          color: white;
          text-transform: uppercase;
          font-family:
            Monument Extended Black,
            sans-serif;
          margin-bottom: 1rem;
        }

        & h2 {
          color: white;
          font-family: JetBrains Mono, monospace;
          font-weight: 400;
          font-size: 1rem;
        }
      }

      & video {
        width: 100%;
        height: 40vh;
        object-fit: cover;
        margin: 2rem 0;
      }
    }

    @media screen and (max-width: 768px) {
      & .mobile-hero {
        display: block;
      }

      & .guarantee {
        font-size: 2rem;
      }
    }

    & .hero {
      position: relative;
      color: white;

      & hgroup {
        position: absolute;
        top: 50%;
        left: 50%;
        transform: translate(-50%, -50%);
        width: 100%;

        text-align: center;
        text-transform: uppercase;

        & h1 {
          text-transform: uppercase;
          font-family:
            Monument Extended Black,
            sans-serif;
          margin-bottom: 1rem;
        }

        & h2 {
          font-family: JetBrains Mono, monospace;
          font-size: 2rem;
        }
      }

      & video {
        width: 100%;
        height: 45vh;
        object-fit: cover;
      }
    }

    @media only screen and (max-width: 1024px) {
      & video {
        height: 40vh;
      }
    }

    @media screen and (max-width: 768px) {
      & .hero {
        display: none;
      }
    }
  }
</style>
