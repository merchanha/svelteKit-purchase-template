<script>
  import { FaqItem, Button } from "$components";
  import twitterIcon from "$assets/icons/twitter.webp";
  import { FAQS } from "../../constants/constans";

  const faqs = FAQS;
  let questionCurrentlyExpand = $state(-1);
  const onclick = (index) => {
    if (questionCurrentlyExpand === index) {
      questionCurrentlyExpand = -1;
    } else {
      questionCurrentlyExpand = index;
    }
  };
</script>

<section class="landing-page-section">
  <h2 class="mb-1">Frequently ask questions</h2>
  <div class="faq-container">
    {#each faqs as faq, index}
      <FaqItem
        {faq}
        isExpanded={index === questionCurrentlyExpand}
        onclick={() => onclick(index)}
      />
    {/each}
  </div>

  <div class="additional-info mt-m">
    <Button class="mt-5">BUY NOW</Button>
    <p class="mt-m">Any other questions?</p>
    <a href="https://x.com/KIZO_ES">
      <p>
        Hit me up on twitter <img
          src={twitterIcon}
          class="twitter-icon"
          alt=""
        />
      </p>
    </a>
  </div>
</section>

<style>
  .additional-info {
    display: flex;
    flex-direction: column;
    align-items: center;
    color: grey;
  }

  .twitter-icon {
    width: 16px;
    height: 16px;
  }

  .additional-info a {
    text-decoration: underline;
  }
</style>
