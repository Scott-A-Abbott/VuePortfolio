<script>
import logo from "./assets/logo.png";

export default {
  name: "App",
  data() {
    return {}
  },
  methods: {},
  render() {
    return (
      <div id="app">
        <img src={logo} />
        <transition>
          <router-view />
        </transition>
      </div>
    );
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
