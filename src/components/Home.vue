<script>
import anime from "animejs";

export default {
  name: "HelloWorld",
  data() {
    return {
      msg: "Welcome to Your Vue.js App",
      slideIn: {},
      slideOut: {},
    };
  },
  methods: {
    nameSlideIn(){
      this.slideIn = anime({
        targets: document.getElementById("name"),
        opacity: 1,
        translateX: '-5vw',
        duration: 700,
        delay: 1000,
        easing: "easeOutQuad"
      })

      this.slideIn.play();
    },
    nameSlideOut(){
      this.slideOut = anime({
        targets: document.getElementById("name"),
        opacity: 0,
        translateX: '-10vw',
        duration: 700,
        delay: 1000,
        easing: "easeOutQuad"
      })

      this.slideOut.play();
    }
    
  },
  render() {
    return (
      <div class="center">
        <transition appear onAfter-appear={this.nameSlideIn} >
          <h1 id="name">SCOTT ABBOTT</h1>
          {/*document.addEventListener('click', this.nameSlideOut)*/}
        </transition>
      </div>
    );
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss" scoped>
div {
  width: 100%;
  height: 100vh;
  overflow: hidden;
}
#name {
  color: #1c1c1c;
  font-size: 12vw;
  opacity: 0;
  position: relative;
  right: -5vw;
}

</style>