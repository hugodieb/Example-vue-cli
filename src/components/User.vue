<template>
    <div class="component">
        <h1>The User Component</h1>
        <p>I'm an awesome User!</p>
        <button type="button" class="btn btn-primary" @click="changeName">Change Name...</button>
        <span>{{name}}</span> /
        <span>{{age}}</span>
        <hr>
        <div class="row">
            <div class="col-xs-12 col-sm-6">
                <app-user-detail :myName="name"
                                  @nameWasReset="name = $event"
                                  @ageWasReset="age = $event"
                                  :resetFn="resetName"
                                  :userAge="age">
                                  </app-user-detail>
            </div>
            <div class="col-xs-12 col-sm-6">
                <app-user-edit :userAge="age"
                                @ageWasReset="age = $event"></app-user-edit>
            </div>
        </div>
    </div>
</template>

<script>
    import UserDetail from './UserDetail.vue';
    import UserEdit from './UserEdit.vue';

    export default {
        data() {
          return {
            name: "Hugo",
            age: 27,
          };
        },
        methods: {
          changeName() {
            this.name = "Mara"
          },
          resetName() {
            this.name = "Hugo"
          },
        },
        components: {
            appUserDetail: UserDetail,
            appUserEdit: UserEdit
        }
    }
</script>

<style scoped>
    div {
        background-color: lightblue;
    }
</style>
