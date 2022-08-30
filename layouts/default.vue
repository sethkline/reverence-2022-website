<template>
  <div>
    <slot name="header">
      <Header></Header>
      <FeaturesList></FeaturesList>
      <ClassAccordion></ClassAccordion>
    </slot>
    <slot />
    <TestimonialCards></TestimonialCards>
    <Footer></Footer>
  </div>
</template>

<script>
export default {
}
</script>
 