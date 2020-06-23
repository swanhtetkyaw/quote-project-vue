
<template>
  <div class="col-sm-6 col-md-4 mb-4">
    <div class="card">
      <div class="card-body quote">
        <blockquote class="blockquote mb-0">
          <p>
            <slot name="content"></slot>
          </p>
          <footer class="blockquote-footer">
            <slot></slot>
            <!-- <cite title="Source Title">Source Title</cite> -->
          </footer>
        </blockquote>
      </div>
    </div>
  </div>
</template>

<script>
export default {};
</script>

<style>
.quote {
  cursor: pointer;
  font-family: "Arizonia", cursive;
  color: #6e6e6e;
}

.quote p {
  font-size: 30px;
}

.quote:hover {
  background-color: #ffe2e2;
}
</style>