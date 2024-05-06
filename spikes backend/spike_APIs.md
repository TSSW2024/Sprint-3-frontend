# Qué es una API

Se trata de un conjunto de definiciones y protocolos que se utiliza para desarrollar e integrar el software de las aplicaciones, permitiendo la comunicación entre dos aplicaciones de software.

Así pues, podemos hablar de una API como una especificación formal que establece cómo un módulo de un software se comunica o interactúa con otro para cumplir una o muchas funciones. Todo dependiendo de las aplicaciones que las vayan a utilizar, y de los permisos que les dé el propietario de la API a los desarrolladores de terceros.

De cara a un usuario normal, lo único que vas a ver de una API son los resultados, cómo abres un juego para el móvil y puedes conectarte a tu cuenta de Facebook para iniciar sesión, o cómo puedes publicar los resultados de una partida en X (Twitter). O cuando esa aplicación te manda notificaciones al móvil o al ordenador.

Las API pueden tener tanto una como varias funciones. Cuando esto pasa, tu aplicación puede enviarle una solicitud con una estructura particular, y esta estructura determinará cómo responderá el servicio o el software al que le estés enviando esa solicitud.

Pueden ser privadas para el uso de una empresa, abiertas sólo para partners, o públicas para que cualquier desarrollador interactuar con ellas o crear sus propias API para que lo hagan. También pueden ser API locales para aplicaciones que se comunican dentro de un mismo ambiente o dispositivo, o remotas para cuando hay que acceder a otro punto diferente.

A los servicios que no son de código abierto también les permite dejar que otros utilicen funciones concretas de sus aplicaciones o servicios sin tener que proporcionarles todo el código. Estos desarrolladores externos podrán utilizar una función sin tener que saber cómo funcionan internamente los procesos que la hacen posible.

## Para qué sirve una API

Una de las principales funciones de las API es poder facilitarle el trabajo a los desarrolladores. Por ejemplo, si estás creando una aplicación que es una tienda online, no necesitarás crear desde cero un sistema de pagos u otro para verificar si hay stock disponible de un producto. Podrás utilizar la API de un servicio de pago ya existente, por ejemplo PayPal, y pedirle a tu distribuidor una API que te permita saber el stock que ellos tienen.

Con ello, no será necesario tener que reinventar la rueda con cada servicio que se crea, ya que podrás utilizar piezas o funciones que otros ya han creado. Imagínate que cada tienda online tuviera que tener su propio sistema de pago, para los usuarios normales es mucho más cómodo poder hacerlo con los principales servicios que casi todos utilizan.

También son útiles para cuando lo único que se quiere es utilizar deliberadamente las funciones de determinado servicio para ofrecer ventajas a sus usuarios o atraer a los usuarios de ese servicio a que utilicen tu aplicación.

Por ejemplo, piensa que quieres crear una aplicación que se conecte a las publicaciones que hay en Twitter, pues para ello tendrás que conectar tu aplicación al servicio mediante la API que Twitter tiene disponible para los desarrolladores.

Otro ejemplo es cuando vas a comprar una entrada a través de la web de una sala de cine. Cuando pones la información de tu tarjeta, la web utiliza una API para enviarle esa información de forma remota a otro programa que verifica si tus datos son correctos o es una tarjeta inventada. Una vez se verifica, este programa remoto le dice a la web que todo está en orden, y esta ya te emite tus entradas.

Además de las ya mencionadas APIs de registro y notificaciones, hay muchas mas APIs y usos para estas pero siento que las mencionadas anteriormente son las más importantes a destacar a la hora de la aplicación de trading.

## Cómo funciona una API

Básicamente las APIs lo que hacen es intercomunicar 2 aplicaciones de diferentes lenguajes, existen distintos tipos de APIs pero las más usadas son las API rest que es un servicio que es capaz de interconectar mediante protocolo HTTP con mensajes de tipo XML o JSON que es el tipo de mensaje más común. Este protocolo se utiliza para la comunicación entre cliente y servidor y permite enviar solicitudes y recibir respuestas, con métodos como GET, POST, PUT y DELETE.

Cada API tiene un endpoint cuya función es que los desarrolladores frontend pueden hacer que la aplicación acceda a esa información, por ejemplo si quisiéramos acceder a una base de datos con una API el endpoint sería algo como `https://dirección/bases_de_datos/usuario`.

Cabe aclarar que lo anterior solo es un ejemplo para mostrar la estructura de cómo se vería un endpoint.

## Cómo llamar a una API de Binance

**Paso 1: Obtener las claves API**

Para esto debes tener una cuenta en Binance y en tu perfil ir a la sección "API Management". Esto para crear una nueva API. Luego se le asigna un nombre a la API y se completa la autenticación. Después de esto se obtendrán dos claves llamadas “API Key” y “Secret Key” que serán utilizadas en el paso 2.

**Paso 2: Autenticación**

Para autenticar las solicitudes a la API de Binance, necesitas incluir tu API Key y tu secret Key en cada solicitud. Esta autenticación se realiza utilizando el encabezado `X-MBX-APIKEY`, que contiene tu clave API.

El encabezado `X-MBX-APIKEY` es un encabezado personalizado utilizado en las solicitudes HTTP a la API de Binance para autenticar y autorizar las acciones realizadas por un usuario o una aplicación.

El encabezado `X-MBX-APIKEY` se utiliza para transmitir la API Key en las solicitudes a la API de Binance. Es un encabezado estándar de HTTP que lleva la clave pública como su valor. Cuando Binance recibe una solicitud con este encabezado, verifica que la clave pública sea válida y autorizada para realizar la acción solicitada.

Y la secret Key se utiliza como una firma digital que se utiliza para firmar cada solicitud y autenticarla correctamente.

**Paso 3: Endpoints y métodos HTTP**

Para acceder a diferentes funciones de la plataforma se utilizan diferentes endpoints. Por ejemplo, existen endpoints para:

- Realizar operaciones
- Obtener información de mercado
- Realizar operaciones de trading
- Etc.

Cada una de estas operaciones tiene un endpoint diferente.

Los endpoints están estrechamente relacionados con los métodos HTTP. Las endpoints pueden ser llamadas con distintos métodos HTTP, por ejemplo:

- GET: Utilizado para obtener información de la API.
- POST: Utilizado para enviar datos a la API para crear algo nuevo.
- DELETE: Utilizado para eliminar recursos de la API.
- PUT: Utilizado para actualizar recursos de la API.

Un ejemplo de cómo se utilizan ambos métodos se demuestra en este código:

```go
package main

import (
    "fmt"
    "io/ioutil"
    "net/http"
)

func main() {
    // URL de la API que quieres llamar
    url := "https://api.binance.com/api/v3/ticker/price?symbol=BTCUSDT"

    // Crear una nueva solicitud HTTP GET
    req, err := http.NewRequest("GET", url, nil)
    if err != nil {
        fmt.Println("Error creando la solicitud:", err)
        return
    }

    // Realizar la solicitud HTTP
    client := &http.Client{}
    resp, err := client.Do(req)
    if err != nil {
        fmt.Println("Error enviando la solicitud:", err)
        return
    }
    defer resp.Body.Close()

    // Verificar el código de estado de la respuesta
    if resp.StatusCode != http.StatusOK {
        fmt.Println("Error: respuesta no exitosa:", resp.Status)
        return
    }

    // Leer la respuesta de la API
    body, err := ioutil.ReadAll(resp.Body)
    if err != nil {
        fmt.Println("Error leyendo la respuesta:", err)
        return
    }

    // Imprimir la respuesta
    fmt.Println("Respuesta de la API:", string(body))
}