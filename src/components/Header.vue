<template>
  <b-navbar toggleable="lg" sticky class="nav-bg">
    <div
      style="display:flex;align-items:center;color:white;background-color:black;align-item:center;height:70px;margin:0;width:255px;padding:0 20px;text-align:right"
      @click="toggleNav"
      class="m-stack m-stack--ver m-stack--general .m-stack--ver"
    >
      <img
        alt="لوگوی سایت آلاء"
        src="https://cdn.alaatv.com/upload/logo_20190508105212_20190512113140.png"
        width="135"
        height="22"
      />
      <div class="m-stack__item m-stack__item--middle m-brand__tools">
        <a
          href="javascript:"
          id="m_aside_left_hide_toggle"
          class="m-brand__icon m-brand__toggler m-brand__toggler--left m--hidden-tablet-and-mobile"
        >
          <span></span>
        </a>
        <a
          id="m_aside_header_menu_mobile_toggle"
          href="javascript:"
          class="m-brand__icon m-brand__toggler m--visible-tablet-and-mobile-inline-block1 d-none"
        >
          <span></span>
        </a>
      </div>
    </div>

    <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>

    <b-collapse id="nav-collapse" is-nav>
      <b-navbar-nav>
        <b-nav-item-dropdown text="فیلم های پایه و کنکور آلاء">
          <b-dropdown-item href="#">EN</b-dropdown-item>
        </b-nav-item-dropdown>

        <b-nav-item-dropdown>
          <template v-slot:button-content>
            <span>همایش کنکوری آلاء</span>
          </template>
          <b-dropdown-item href="#">Profile</b-dropdown-item>
          <b-dropdown-item href="#">Sign Out</b-dropdown-item>
        </b-nav-item-dropdown>
      </b-navbar-nav>
      <b-navbar-nav class="ml-0 mr-auto">
        <b-nav-item href="#">
          ورود/ثبت نام
          <span class="m-nav__link-icon">
            <i class="fa fa-sign-in-alt"></i>
          </span>
        </b-nav-item>
      </b-navbar-nav>
    </b-collapse>
  </b-navbar>
</template>

<script>
export default {
  name: "Header",
  data() {
    return {
      menuIsOpen: false,
    };
  },
  methods: {
    toggleNav: function () {
      this.menuIsOpen = !this.menuIsOpen;
      if (this.menuIsOpen) {
        document.getElementById("mySidenav").style.width = "255px";
        document.getElementById("main").style.marginRight = "255px";
      } else {
        document.getElementById("mySidenav").style.width = "0";
        document.getElementById("main").style.marginRight = "0";
      }
    },
  },
};
</script>
<style scoped>
.nav-bg {
  padding: 0 0 0 20px;
  background-color: #ff9000;
}
@media (max-width: 991.98px) {
  .nav-bg {
    background-color: black;
  }
}
</style>