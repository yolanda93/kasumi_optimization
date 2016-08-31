# kasumi_optimization
Implementation and optimization of kasumi cipher algorithm 

KASUMI, es un cifrador por bloques, usado en los estándares UMTS, GSM y GPRS de comunicaciones móviles. En UMTS se utiliza en algoritmos de confidencialidad, f8, e integridad, f9, con nombres UEA1 y UIA1, respectivamente. En GSM es usado como generador de claves en el algoritmo A5/3 y en GPRS se usa también como generador de claves para el GEA3 [1]. Fue diseñado por el grupo SAGE y está basado en MISTY1 con algunas modificaciones para su implementación hardware.


En el estándar ETSI TS 135 202 v7.0.0. (2007-06) en el criptoanálisis inicial que se realizó se comprobó su firmeza ante el criptoanálisis diferencial y en un principio se consiguió optimizar el algoritmo para su implementación hardware sin afectar a la seguridad que ya tenía MISTY1. Por tanto, se proponen ataques derivados del criptoanálisis diferencial, el primero que tuvo éxito en 2001 por Kühn,Ulrich (Eurocrypt) fue un ataque diferencial imposible en la etapa 6 del algoritmo.

Mientras el ataque diferencial se basa en el análisis de la evolución de las diferencias de dos textos en claro relacionados cuando son encriptados con la misma clave, asignando probabilidades a cada una de las claves posibles para identificar la clave correcta o más probable. El ataque diferencial imposible sigue el mismo concepto pero asigna probabilidades con valor 0, es decir, determina el conjunto de claves que no pueden darse para el caso a analizar.


Finalmente se logró romper el algoritmo en 2010 con el denominado “sandwich attack” (Dunkelman, Keller, and Shamir) [5] para el cual se necesitaban las claves relativas pero que logra recuperar la clave completamente. Aunque en el estándar no contempla este tipo de ataques como amenaza ya que es difícil que se den las condiciones necesarias para recuperar las claves relativas necesarias, este tipo de ataque no tiene el mismo éxito en MISTY demostrando así que Kasumi es criptográficamente más débil al contrario de lo que se creía en un principio.
