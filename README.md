# 🏛️ API REST de Conversión de Números Romanos y Arábigos

## Descripción del Proyecto

Este proyecto es una API RESTful construida con **Node.js y Express** para la conversión bidireccional de números entre el sistema de numeración romano y el sistema arábigo (decimal).

Cumple con los requisitos de la actividad del profesor, incluyendo un traductor robusto, pruebas unitarias con Jest, y un despliegue en la plataforma Vercel.

## ✅ Requisitos de la Actividad Cumplidos

| Requisito | Estado |
| :--- | :--- |
| **1. Crear un traductor de Romano a Arábigo** | ✅ Implementado (`romanToArabic`) |
| **2. Crear un traductor de Arábigo a Romano** | ✅ Implementado (`arabicToRoman`) |
| **3. API compatible con el formato del profesor** | ✅ Implementado (Endpoints `/r2a/:romanNum` y `/a2r/:arabicNum`) |
| **4. Implementar Tests Unitarios** | ✅ Implementado (Jest) |
| **5. Despliegue en Vercel** | 🚀 Listo para ser desplegado |

---

## 💻 Tecnologías Utilizadas

* **Backend:** Node.js
* **Framework Web:** Express
* **Tests:** Jest
* **Plataforma de Despliegue:** Vercel

---

## 🔗 Endpoints de la API

La API expone dos endpoints a través de parámetros de ruta (URL params) para realizar las conversiones.

### 1. Conversión de Romano a Arábigo (R2A)

Convierte un número romano (de 1 a 3999) a su equivalente arábigo.

* **Método:** `GET`
* **Ruta:** `/r2a/:romanNum`
* **Parámetro:** `romanNum` (Ej. `IV`, `XIX`, `MCMXCIV`)

#### Ejemplo:

| Solicitud (URL) | Respuesta JSON (200 OK) |
| :--- | :--- |
| `/r2a/MCMXCIV` | `{"roman": "MCMXCIV", "arabic": 1994}` |

---

### 2. Conversión de Arábigo a Romano (A2R)

Convierte un número arábigo (de 1 a 3999) a su equivalente romano.

* **Método:** `GET`
* **Ruta:** `/a2r/:arabicNum`
* **Parámetro:** `arabicNum` (Ej. `4`, `19`, `1994`)

#### Ejemplo:

| Solicitud (URL) | Respuesta JSON (200 OK) |
| :--- | :--- |
| `/a2r/4` | `{"arabic": 4, "roman": "IV"}` |

---

### Manejo de Errores

La API utiliza un *middleware* de errores global que detecta fallos de validación (ej. números fuera de rango, símbolos no válidos) y devuelve una respuesta con código **400 Bad Request**.

| Solicitud (URL) | Respuesta JSON (400 Bad Request) |
| :--- | :--- |
| `/r2a/IIA` | `{"error": "Error", "message": "Simbolos no válidos encontrador..."}` |
| `/a2r/4000` | `{"error": "RangeError", "message": "El número arábigo debe estar entre 1 y 3999."}` |

---

## 🚀 Despliegue y Uso Local

### Instalación de Dependencias

Para instalar todas las dependencias del proyecto (incluyendo `express` y `jest`), ejecuta:

```bash
npm install
