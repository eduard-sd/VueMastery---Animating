<template>
  <div class="list">
    <input type="text" v-model="newContact" placeholder="Name">
    <button @click="addContact">Add</button>
    <button @click="sort">Sort</button>

    <transition-group name="slide-up" tag="ul" appear>
      <li v-for="contact in contactList" :key="contact">
        {{ contact }}
      </li>
    </transition-group>
  </div>
</template>

<script>
export default {
  data() {
    return {
      newContact: "",
      contactList: [
        "Beu Losdon",
        "Henry Holl",
        "David Peeters"
      ]
    };
  },
  methods: {
    addContact() {
      if (this.newContact) {
        this.contactList.push(this.newContact);
        this.newContact = ""
      }
    },
    sort() {
      if (this.contactList && this.contactList.length) {
        this.contactList = this.contactList.sort()
      }
    }
  }
}
</script>
