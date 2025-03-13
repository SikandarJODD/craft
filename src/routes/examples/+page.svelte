<script>
  import Container from "$lib/components/blocks/craft/Container.svelte";
  import Prose from "$lib/components/blocks/craft/Prose.svelte";
  import Section from "$lib/components/blocks/craft/Section.svelte";

  import Img1 from "$lib/images/blogimg.svg";
  import Img2 from "$lib/images/blog2.svg";
  import Img3 from "$lib/images/blog3.svg";
  let contents = [
    {
      name: "Sveltekit Blog",
      link: "/examples/blog",
      desc: "blog is build using svelte craft",
      img: Img1,
    },
    {
      name: "Article",
      link: "/examples/article",
      desc: "article is build using svelte craft",
      img: Img2,
    },
    {
      name: "Markdown Blog",
      link: "/examples/markdown",
      desc: "blog is build using markdown & svelte craft",
      img: Img3,
    },
  ];
</script>

<Prose>
  <Section class='!py-0'>
    <Container class='!py-0'>
      <h3>Examples</h3>
      <div class="w-full mt-2 grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3">
        {#each contents as content}
          <a href={content.link} class="no-underline!">
            <img class="mb-1!" src={content.img} alt={content.name} />
            <h6>{content.name}</h6>
            <p class="text-sm! text-muted-foreground">{content.desc}</p>
          </a>
        {/each}
      </div>
    </Container>
  </Section>
</Prose>
