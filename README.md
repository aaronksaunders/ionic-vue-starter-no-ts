# ionic-starter-no-ts


- Check out my [YouTube channel](https://www.youtube.com/channel/UCMCcqbJpyL3LAv3PJeYz2bg) with great Ionic Framework Content
- Follow Me On [Twitter](https://twitter.com/aaronksaunders)
- Read my technical content on [dev.to](https://dev.to/aaronksaunders)
- [Join The Newsletter](https://fiwic.ck.page/0bea0cd20d) for content updates and information on upcoming courses

### Includes
- Using a Modal
- Using a Toast
- Page Navigation
- Detail Page Navigation
- Using IonIcons
- Structuring Vue SFC the v2 way
```
export default defineComponent({
  name: "Home",
  components: {
    IonContent,
    IonHeader,
    IonPage,
    IonTitle,
    IonToolbar
  },
  data() {
    return {
      addCircleOutline
    };
  },
  methods: {
    goDetailPage() {
      this.$router.push("/detail");
    }
  }
});
```
