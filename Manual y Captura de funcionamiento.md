Componente Boton
```js
<template>
    <ion-button
      :color="color1"
      :expand="expand"
      :size="size"
      :fill="fill"
      :disabled="disabled"
      @click="handleClick"
    >
      <slot></slot>
    </ion-button>
    <ion-button
      :color="color1"
      :expand="expand"
      :size="size"
      :fill="fill2"
      :disabled="true"
      @click="handleClick"
    >
      <slot></slot>
    </ion-button>
    <ion-button
      :color="color"
      :expand="expand"
      :size="size1"
      :fill="fill1"
      :disabled="false"
      @click="handleClick"
    >
      <slot></slot>
    </ion-button>
    <ion-button
      :color="color2"
      :expand="expand"
      :size="size1"
      :fill="fill2"
      :disabled="false"
      @click="handleClick"
    >
      <slot></slot>
    </ion-button>
  </template>
  
  <script>
  import { defineComponent } from 'vue';
  import { IonButton } from '@ionic/vue';
  
  export default defineComponent({
    name: 'Boton',
    components: { IonButton },
    props: {
      color1: {
        type: String,
        default: 'danger', // Colores de Ionic como 'primary', 'secondary', 'danger', etc.
      },
      color2: {
        type: String,
        default: 'secondary', // Colores de Ionic como 'primary', 'secondary', 'danger', etc.
      },
      expand: {
        type: String,
        default: 'block', // 'block', 'full' o vacío
      },
      size: {
        type: String,
        default: 'large', // 'small', 'default', 'large'
      },
      fill1: {
        type: String,
        default: 'clear', // 'clear', 'outline', 'solid' 
      },
      fill2: {
        type: String,
        default: 'outline', // 'clear', 'outline', 'solid' 
      },
      disabled: {
        type: Boolean,
        default: false,
      },
    },
    methods: {
      handleClick() {
        this.$emit('click');
      },
    },
  });
  </script>
  
  <style scoped>
  /* Puedes añadir estilos personalizados aquí si deseas */
  </style>
  
```
  Componente Tarjeta
```js
  <template>
    <ion-card>
      <ion-card-header v-if="title || subtitle">
        <ion-card-title v-if="title">{{ title }}</ion-card-title>
        <ion-card-subtitle v-if="subtitle">{{ subtitle }}</ion-card-subtitle>
      </ion-card-header>
  
 <ion-card-content>
        <slot></slot>
      </ion-card-content>
  
<ion-img v-if="image" :src="image" />
 </ion-card>
    <ion-card>
      <ion-card-header v-if="title || subtitle">
        <ion-card-title v-if="title">{{ title1 }}</ion-card-title>
        <ion-card-subtitle v-if="subtitle">{{ subtitle }}</ion-card-subtitle>
      </ion-card-header>
  
<ion-card-content>
        <slot></slot>
      </ion-card-content>
  
<ion-img v-if="image" :src="image" />
    </ion-card>
    <ion-card>
      <ion-card-header v-if="title || subtitle">
        <ion-card-title v-if="title">{{ title1 }}</ion-card-title>
        <ion-card-subtitle v-if="subtitle">{{ subtitle1 }}</ion-card-subtitle>
      </ion-card-header>
  
<ion-card-content>
        <slot></slot>
      </ion-card-content>
  
 <ion-img v-if="image" :src="image" />
    </ion-card>
  </template>
  
  <script>
  import { defineComponent } from 'vue';
  import { IonCard, IonCardHeader, IonCardTitle, IonCardSubtitle, IonCardContent, IonImg } from '@ionic/vue';
  
  export default defineComponent({
    name: 'ComponentCard',
    components: {
      IonCard,
      IonCardHeader,
      IonCardTitle,
      IonCardSubtitle,
      IonCardContent,
      IonImg,
    },
    props: {
      title: {
        type: String,
        default: 'Esto es una card',
      },
      title1: {
        type: String,
        default: 'Esto es una card con un titulo distinto',
      },
      subtitle: {
        type: String,
        default: 'este es el subtitulo',
      },
      subtitle1: {
        type: String,
        default: 'este es el subtitulo pero tambien es distinto',
      },
      image: {
        type: String,
        default: "aqui se puede poner una imagen",
      },
    },
  });
  </script>
  
  <style scoped>
  /* Puedes añadir estilos personalizados aquí si deseas */
  </style>
  
```

  Componente Input
```js
  <template>
    <ion-item>
      <ion-label :for="id">{{ nombre }}&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</ion-label>
      <ion-input
        :id="id"
        :value="value"
        @ionChange="$emit('update:value', $event.detail.value)"
        :placeholder="placeholder"
      ></ion-input>
    </ion-item>
    <ion-item>
      <ion-label :for="id">{{ nombre }}&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</ion-label>
      <ion-input
        :id="id"
        :value="value"
        @ionChange="$emit('update:value', $event.detail.value)"
        :placeholder="placeholder1"
      ></ion-input>
    </ion-item>
    <ion-item>
      <ion-label :for="id">{{ nombre }}&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</ion-label>
      <ion-input
        :id="id"
        :value="value"
        @ionChange="$emit('update:value', $event.detail.value)"
        :placeholder="placeholder2"
      ></ion-input>
    </ion-item>
  </template>
  
  <script>
  import { IonItem, IonLabel, IonInput } from '@ionic/vue';
  
  export default {
    name: 'CustomInput',
    components: {
      IonItem,
      IonLabel,
      IonInput,
    },
    props: {
      id: {
        type: String,
        required: true,
      },
      nombre: {
        type: String,
        required: true,
      },
      value: {
        type: String,
        default: '',
      },
      placeholder: {
        type: String,
        default: 'Enter value...',
      },
      placeholder1: {
        type: String,
        default: 'Ingrese un valor...',
      },
      placeholder2: {
        type: String,
        default: 'Введите значение...',
      },
    },
  };
  </script>
  
  <style scoped>
  ion-item {
    margin: 10px 0;
    background-color: aquamarine;
    font-family: 'Franklin Gothic Medium', 'Arial Narrow', Arial, sans-serif;
    margin-top: 5%;
  }
  </style>

```

  Componente CRUD
```js
  <template>
    
 <ion-item lines="none">
    <ion-button color="primary" @click="$emit('create')" expand="block">
      Crear
    </ion-button>
    <ion-button color="medium" @click="$emit('read')" expand="block">
      Leer
    </ion-button>
    <ion-button color="warning" @click="$emit('update')" expand="block">
      Actualizar
    </ion-button>
    <ion-button color="danger" @click="$emit('delete')" expand="block">
      Eliminar
    </ion-button>
  </ion-item>
  </template>
  
  <script>
  import { IonItem, IonLabel, IonInput } from '@ionic/vue';
  
  export default {
    name: 'ComponentCrud',
    components: {
      IonItem,
      IonLabel,
      IonInput,
    },
    props: {
      id: {
        type: String,
        required: true,
      },
      nombre: {
        type: String,
        required: true,
      },
      value: {
        type: String,
        default: '',
      },
      placeholder: {
        type: String,
        default: 'Enter value...',
      },
    },
  };
  </script>
  
  <style scoped>
  ion-item {
    margin: 10px 0;
  }
  </style>
  
  ```
  Componente Formulario
```js
<template>
    <form @submit.prevent="handleSubmit">
      <ion-item>
        <ion-label position="floating">Nombre:</ion-label>
        <ion-input v-model="formData.name" required></ion-input>
      </ion-item>
  
<ion-item>
        <ion-label position="floating">Correo Electrónico:</ion-label>
        <ion-input v-model="formData.email" type="email" required></ion-input>
      </ion-item>
  
<ion-item>
        <ion-label position="floating">Mensaje:</ion-label>
        <ion-textarea v-model="formData.message" required></ion-textarea>
      </ion-item>
  
<div v-if="formErrors.length" class="errors">
        <p>Por favor corrige los siguientes errores:</p>
        <ul>
          <li v-for="(error, index) in formErrors" :key="index">{{ error }}</li>
        </ul>
      </div>
  
<ion-button type="submit" expand="block">Enviar</ion-button>
    </form>
  </template>
  
  <script>
  import { IonItem, IonLabel, IonInput, IonTextarea, IonButton } from '@ionic/vue';
  
  export default {
    name: 'ComponentFormulario',
    components: {
      IonItem,
      IonLabel,
      IonInput,
      IonTextarea,
      IonButton
    },
    data() {
      return {
        formData: {
          name: '',
          email: '',
          message: ''
        },
        formErrors: []
      };
    },
    methods: {
      validateForm() {
        this.formErrors = [];
  
        if (!this.formData.name) {
          this.formErrors.push("El nombre es obligatorio.");
        }
        if (!this.formData.email) {
          this.formErrors.push("El correo electrónico es obligatorio.");
        } else if (!/\S+@\S+\.\S+/.test(this.formData.email)) {
          this.formErrors.push("El correo electrónico no es válido.");
        }
        if (!this.formData.message) {
          this.formErrors.push("El mensaje es obligatorio.");
        }
  
        return this.formErrors.length === 0;
      },
      handleSubmit() {
        if (this.validateForm()) {
          alert('Formulario enviado correctamente!');
          // Puedes enviar los datos a un servidor aquí, o realizar otras acciones
          this.resetForm();
        }
      },
      resetForm() {
        this.formData = {
          name: '',
          email: '',
          message: ''
        };
      }
    }
  };
  </script>
  
  <style scoped>
  .errors {
    color: red;
    margin: 10px 0;
  }
  </style>
  
```
  Componente en grupo

```js
  <template>
  <ion-card>
    <ion-card-header>
      <ion-card-title>{{ cardTitle }}</ion-card-title>
      <ion-card-subtitle>{{ cardSubtitle }}</ion-card-subtitle>
    </ion-card-header>

<ion-card-content>
      <!-- Contenido de la tarjeta -->
      <p>{{ cardContent }}</p>

<!-- Input para capturar datos -->
<ion-item>
        <ion-label position="floating">Escribe algo:</ion-label>
        <ion-input v-model="inputText" placeholder="" clear-input></ion-input>
      </ion-item>

<!-- Botón para actualizar contenido -->
<ion-button expand="block" color="primary" @click="updateCardContent">
     Actualizar contenido
      </ion-button>
    </ion-card-content>
  </ion-card>
</template>

<script>
import { defineComponent, ref } from 'vue';
import {
  IonCard,
  IonCardHeader,
  IonCardTitle,
  IonCardSubtitle,
  IonCardContent,
  IonItem,
  IonLabel,
  IonInput,
  IonButton,
} from '@ionic/vue';

export default defineComponent({
  name: 'ComponentGrupo',
  components: {
    IonCard,
    IonCardHeader,
    IonCardTitle,
    IonCardSubtitle,
    IonCardContent,
    IonItem,
    IonLabel,
    IonInput,
    IonButton,
  },
  props: {
    cardTitle: {
      type: String,
      default: 'Título de la Tarjeta',
    },
    cardSubtitle: {
      type: String,
      default: 'Subtítulo de la Tarjeta',
    },
  },
  setup() {
    const inputText = ref('');
    const cardContent = ref('Aquí se mostrará el contenido.');

    const updateCardContent = () => {
      cardContent.value = inputText.value || 'Campo vacío';
      inputText.value = '';
    };

    return {
      inputText,
      cardContent,
      updateCardContent,
    };
  },
});
</script>

<style scoped>
/* Puedes añadir estilos personalizados aquí si deseas */
</style>

```

    Vista

```js
  <template>
  <ion-page>
    <ion-header :translucent="true">
      <ion-toolbar>
        <ion-title>Blank</ion-title>
      </ion-toolbar>
    </ion-header>

<ion-content :fullscreen="true">
      <ion-header collapse="condense">
        <ion-toolbar>
          <ion-title size="large">Blank</ion-title>
        </ion-toolbar>
      </ion-header>

<div id="container">
        <strong>Ready to create an app?</strong>
        <p>Start with Ionic <a target="_blank" rel="noopener noreferrer" href="https://ionicframework.com/docs/components">UI Components</a></p>
      </div>

     
<custom-input></custom-input>
     <boton></boton>
     <component-card> </component-card>
     <component-crud></component-crud>
     <component-formulario></component-formulario>
     <component-grupo></component-grupo> 

      
</ion-content>
  </ion-page>
</template>

<script setup lang="ts">
import { IonContent, IonHeader, IonPage, IonTitle, IonToolbar } from '@ionic/vue';
import CustomInput from '../components/CustomInput.vue';
import ComponentCrud from '@/components/ComponentCrud.vue';
import ComponentFormulario from '@/components/ComponentFormulario.vue';
import ComponentGrupo from '@/components/ComponentGrupo.vue';
import Boton from '@/components/Boton.vue';
import ComponentCard from '@/components/ComponentCard.vue';
</script>

<style scoped>
#container {
  text-align: center;
  
  position: absolute;
  left: 0;
  right: 0;
  top: 50%;
  transform: translateY(-50%);
}

#container strong {
  font-size: 20px;
  line-height: 26px;
}

#container p {
  font-size: 16px;
  line-height: 22px;
  
  color: #8c8c8c;
  
  margin: 0;
}

#container a {
  text-decoration: none;
}
</style>

 ```
Captura de funcionamiento


![Evidencia](imagenes\imagen1.png)

![Evidencia](imagenes\imagen2.png)

![Evidencia](imagenes\imagen3.png)
