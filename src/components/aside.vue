<!-- eslint-disable prettier/prettier -->

<!-- eslint-disable prettier/prettier -->
<template>
  <aside>
    <div :class="['social-media']">
      <ul>
        <li>
          <button
            type="button"
            class="btn btn-info"
            data-bs-toggle="modal"
            data-bs-target="#tahu1"
          >
            <i class="bi bi-droplet-half"></i>
          </button>
        </li>
      </ul>
    </div>
    <div></div>
  </aside>
  <!-- Modal -->
  <div
    class="modal fade"
    id="tahu1"
    tabindex="-1"
    aria-labelledby="exampleModalLabel"
    aria-hidden="true"
  >
    <div class="modal-dialog modal-dialog-centered modal-lg">
      <div class="modal-content">
        <div class="modal-header">
          <h1 class="modal-title fs-5" id="tahu1">Taukah Kamu???</h1>
          <button
            type="button"
            class="btn-close"
            data-bs-dismiss="modal"
            aria-label="Close"
          ></button>
        </div>
        <div class="modal-body">
          <!-- tahukah kamu 1 -->
          <div class="choose-image">
            <img src="../assets/img/TAHUKAH-KAMU-1.jpg" alt="tahu 1" />
          </div>
        </div>
        <div class="modal-footer">
          <button
            class="btn btn-outline-primary"
            data-bs-target="#tahu2"
            data-bs-toggle="modal"
          >
            <i class="bi bi-caret-right-fill"></i>
          </button>
        </div>
      </div>
    </div>
  </div>
  <div
    class="modal fade"
    id="tahu2"
    aria-hidden="true"
    aria-labelledby="exampleModalToggleLabel2"
    tabindex="-1"
  >
    <div class="modal-dialog modal-dialog-centered modal-lg">
      <div class="modal-content">
        <div class="modal-header">
          <h1 class="modal-title fs-5" id="tahu2">Taukah Kamu???</h1>
          <button
            type="button"
            class="btn-close"
            data-bs-dismiss="modal"
            aria-label="Close"
          ></button>
        </div>
        <div class="modal-body">
          <div class="choose-image">
            <img src="../assets/img/no2.jpg" alt="tahu 2" />
          </div>
        </div>
        <div class="modal-footer">
          <button
            class="btn btn-outline-primary"
            data-bs-target="#tahu1"
            data-bs-toggle="modal"
          >
            <i class="bi bi-caret-left-fill"></i>
          </button>
          <button
            class="btn btn-outline-primary"
            data-bs-target="#tahu3"
            data-bs-toggle="modal"
          >
            <i class="bi bi-caret-right-fill"></i>
          </button>
        </div>
      </div>
    </div>
  </div>
  <div
    class="modal fade"
    id="tahu3"
    aria-hidden="true"
    aria-labelledby="exampleModalToggleLabel2"
    tabindex="-1"
  >
    <div class="modal-dialog modal-dialog-centered modal-lg">
      <div class="modal-content">
        <div class="modal-header">
          <h1 class="modal-title fs-5" id="exampleModalToggleLabel2">
            Taukah Kamu???
          </h1>
          <button
            type="button"
            class="btn-close"
            data-bs-dismiss="modal"
            aria-label="Close"
          ></button>
        </div>
        <div class="modal-body">
          <div class="choose-image">
            <img src="../assets/img/no3.jpg" alt="tahu 3" />
          </div>
        </div>
        <div class="modal-footer">
          <button
            class="btn btn-outline-primary"
            data-bs-target="#tahu2"
            data-bs-toggle="modal"
          >
            <i class="bi bi-caret-left-fill"></i>
          </button>
          <button
            class="btn btn-outline-primary"
            data-bs-target="#tahu4"
            data-bs-toggle="modal"
          >
            <i class="bi bi-caret-right-fill"></i>
          </button>
        </div>
      </div>
    </div>
  </div>
  <div
    class="modal fade"
    id="tahu4"
    aria-hidden="true"
    aria-labelledby="exampleModalToggleLabel2"
    tabindex="-1"
  >
    <div class="modal-dialog modal-dialog-centered modal-lg">
      <div class="modal-content">
        <div class="modal-header">
          <h1 class="modal-title fs-5" id="exampleModalToggleLabel2">
            Taukah Kamu???
          </h1>
          <button
            type="button"
            class="btn-close"
            data-bs-dismiss="modal"
            aria-label="Close"
          ></button>
        </div>
        <div class="modal-body">
          <div class="choose-image">
            <img src="../assets/img/no4.jpg" alt="tahu 4" />
          </div>
        </div>
        <div class="modal-footer">
          <button
            class="btn btn-outline-primary"
            data-bs-target="#tahu3"
            data-bs-toggle="modal"
          >
            <i class="bi bi-caret-left-fill"></i>
          </button>
          <button
            class="btn btn-outline-primary"
            data-bs-dismiss="modal"
            aria-label="Close"
          >
          <i class="bi bi-check-lg"></i>
          </button>
        </div>
      </div>
    </div>
  </div>
</template>
<!-- eslint-disable prettier/prettier -->
<script>
export default {
  data() {
    return {
      isTop: false
    }
  },
}
</script>
