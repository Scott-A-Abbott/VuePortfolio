<script>
import anime from "animejs";

export default {
  name: "HelloWorld",
  data() {
    return {
      msg: "Welcome to Your Vue.js App",
      animate: {}
    };
  },
  methods: {
    afterAppear() {
      this.animate = anime({
        targets: document.getElementById("message"),
        opacity: "1",
        duration: 2000,
        easing: "linear",
        delay: 2000,
        complete() {
          console.log(`complete: ${new Date(Date.now()).toLocaleTimeString()}`);
        }
      });

      this.animate.play();
    }
  },
  render() {
    return (
      <div class="hello">
        <transition appear onAfter-appear={this.afterAppear}>
          <h1 id="message">{this.msg}</h1>
        </transition>
      </div>
    );
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss" scoped>
$n: normal;
$color: red;
#message {
  opacity: 0;
}
h1,
h2 {
  font-weight: $n;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: $color;
}
</style>