---
title: A.25   Beispiele der copyprivate-Datenattributklausel
ms.date: 11/04/2016
ms.assetid: 7b1cb6a5-5691-4b95-b3ac-d7543ede6405
ms.openlocfilehash: 6c3c174780023f17cc2aa47a54bff14fccf99306
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50493886"
---
# <a name="a25---examples-of-the-copyprivate-data-attribute-clause"></a>A.25   Beispiele der copyprivate-Datenattributklausel

**Beispiel 1:** der `copyprivate` Klausel ([Abschnitt 2.7.2.8](../../parallel/openmp/2-7-2-8-copyprivate.md) auf 32) senden, die von einem einzelnen Thread direkt für alle Instanzen der privaten Variablen in anderen Threads abgerufene Werte verwendet werden können.

```
float x, y;
#pragma omp threadprivate(x, y)

void init( )
{
    float a;
    float b;

    #pragma omp single copyprivate(a,b,x,y)
    {
        get_values(a,b,x,y);
    }

    use_values(a, b, x, y);
}
```

Wenn Sie routinemäßige *Init* heißt aus einer seriellen Region, ist das Verhalten nicht durch das Vorhandensein der Richtlinien betroffen. Nach dem Aufruf der *Get_values* Routine von einem Thread ausgeführt wurde, kein Thread das Konstrukt verlässt, bis die private Objekte, die vom angegebenen *eine*, *b*, *x*, und *y* in allen Threads haben mit den Werten lesen definiert werden.

**Beispiel 2:** im Gegensatz zum vorherigen Beispiel nehmen wir an der Lesevorgang von einem bestimmten Thread, z. B. die master-Thread ausgeführt werden muss. In diesem Fall die `copyprivate` Klausel nicht verwendet werden, die Übertragung direkt zu tun, aber es kann verwendet werden, um den Zugriff auf ein temporäres Objekt des freigegebenen ermöglichen.

```
float read_next( )
{
    float * tmp;
    float return_val;

    #pragma omp single copyprivate(tmp)
    {
        tmp = (float *) malloc(sizeof(float));
    }

    #pragma omp master
    {
        get_float( tmp );
    }

    #pragma omp barrier
    return_val = *tmp;
    #pragma omp barrier

    #pragma omp single
    {
       free(tmp);
    }

    return return_val;
}
```

**Beispiel 3:** nehmen wir an, dass die Anzahl der Sperrobjekte, die erforderlich sind, innerhalb eines parallelen Bereichs problemlos bestimmt werden kann, bevor Sie eingeben. Die `copyprivate` -Klausel kann verwendet werden, um den Zugriff auf freigegebene Sperrobjekte bereitzustellen, die innerhalb dieser parallelen Bereichs zugeordnet werden.

```
#include <omp.h>

omp_lock_t *new_lock()
{
    omp_lock_t *lock_ptr;

    #pragma omp single copyprivate(lock_ptr)
    {
        lock_ptr = (omp_lock_t *) malloc(sizeof(omp_lock_t));
        omp_init_lock( lock_ptr );
    }

    return lock_ptr;
}
```