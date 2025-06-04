# Playwright
## Descripción del Proyecto
Playwright Pacifico es un proyecto de pruebas automatizadas diseñado para validar el flujo de compra en la aplicación Sauce Demo. Este proyecto utiliza **Playwright** como framework de automatización y **Cucumber** para la definición de escenarios en lenguaje Gherkin, siguiendo el patrón de diseño **Page Object Model (POM)**.

El objetivo principal es garantizar que los usuarios puedan iniciar sesión, agregar productos al carrito y completar una compra, cumpliendo con los criterios de aceptación definidos.
## Explicación de la Estructura

### **1. config/**
Contiene configuraciones del proyecto, como el archivo `cucumber.js` para Cucumber.

### **2. src/features/**
Contiene los archivos `.feature` escritos en Gherkin, que describen los escenarios de prueba:
- **`login.feature`**: Escenarios relacionados con el inicio de sesión.
- **`cart.feature`**: Escenarios relacionados con el carrito de compras.
- **`checkout.feature`**: Escenario relacionados con el proceso de compra.

### **3. src/pages/**
Implementa el patrón **Page Object Model (POM)**, encapsulando la lógica de interacción con las páginas:
- **`loginPage.ts`**: Métodos para interactuar con la página de inicio de sesión.
- **`productsPage.ts`**: Métodos para interactuar con la página de productos.
- **`checkoutPage.ts`**: Métodos para interactuar con la página de checkout.

### **4. src/stepDefinitions/**
Contiene las implementaciones de los pasos definidos en los archivos `.feature`:
- **`loginSteps.ts`**: Pasos para los escenarios de inicio de sesión.
- **`cartSteps.ts`**: Pasos para los escenarios del carrito de compras.
- **`checkoutSteps.ts`**: Pasos para los escenarios del proceso de compra.

### **5. test-results/**
Carpeta donde se almacenan los resultados de las pruebas (HTML, JSON, etc.).

### **6. package.json**
Archivo que define las dependencias del proyecto y los scripts de ejecución.

### **7. tsconfig.json**
Configuración de TypeScript para el proyecto.

### **8. README.md**
Documentación del proyecto.

---

## Requisitos Previos
Antes de ejecutar el proyecto, asegúrate de tener instalados los siguientes componentes:
- **Node.js** (v16 o superior)
- **npm** (incluido con Node.js)
- **Playwright** (instalado como dependencia del proyecto)

---

## Instalación
1. Clona el repositorio:
   ```bash
   git clone <URL_DEL_REPOSITORIO>
   cd playwright-pacifico
   ```

2. Instala las dependencias:
   ```bash
   npm install
   ```

3. Instala los navegadores necesarios para Playwright:
   ```bash
   npx playwright install
   ```

---

## Ejecución de Pruebas

### Ejecutar todos los escenarios:
```bash
npx cucumber-js
```

### Ejecutar escenarios específicos por etiqueta:
- Escenarios de inicio de sesión:
  ```bash
  npx cucumber-js --tags @login_ingresar
  ```
- Escenarios del carrito de compras:
  ```bash
  npx cucumber-js --tags @carrito_agregar
  ```
- Escenarios del proceso de compra:
  ```bash
  npx cucumber-js --tags @Checkout
  ```
## Patrones de Diseño
El proyecto utiliza el patrón **Page Object Model (POM)** para mantener el código modular y reutilizable. Cada página de la aplicación está representada por una clase que encapsula los selectores y métodos necesarios para interactuar con los elementos de la página.

## Resultados de las Pruebas
Los resultados de las pruebas se generan en formato **HTML** y **JSON** en la carpeta `test-results/`. Para visualizar el reporte HTML:
1. Ejecuta las pruebas.
2. Abre el archivo `test-results/reports/cucumber-report.html` en tu navegador.

## Notas Adicionales
- **Usuarios de Prueba:**
  - Usuario estándar: `standard_user`
  - Usuario bloqueado: `locked_out_user`
  - Contraseña para ambos: `secret_sauce`
- **Navegadores Compatibles:** Playwright soporta Chromium, Firefox y WebKit. Asegúrate de que los navegadores estén instalados correctamente.
