```js
 props:{
     type: String,
    default: "success",
    required: true,
    validator: function(value){ return ["success", "warning", "error"].indexOf(value) !== -1; }
},
computed: {
    toastType() {
        return `toast-${this.getType}`;
    },
    toastIcon() {
        return `icon-${this.getType}`
    },
    getType() {
        return ["success", "warning", "error"].indexOf(this.type) === -1? "success":this.type
    },
    toastTitle() {
        return this.title ? this.title : this.type.charAt(0).toUpperCase() + this.type.slice(1);
    }
},
components: {
    IconError,
    IconWarning,
    IconSuccess,
}
```
