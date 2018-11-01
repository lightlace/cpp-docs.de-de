---
title: A.29   Verwenden von Arbeitsteilungskonstrukten innerhalb eines critical-Konstrukts
ms.date: 11/04/2016
ms.assetid: d5c8a83f-2f51-4f23-8ddf-d267e347507f
ms.openlocfilehash: fac5576f859f63298d658b51c4307bb238e301c8
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50643585"
---
# <a name="a29---use-of-work-sharing-constructs-inside-a-critical-construct"></a>A.29   Verwenden von Arbeitsteilungskonstrukten innerhalb eines critical-Konstrukts

Im folgende Beispiel wird veranschaulicht, mit einem Konstrukt Freigabe von Arbeit in einem `critical` zu erstellen. In diesem Beispiel ist kompatibel, da die Arbeit-Freigabe zu erstellen und die `critical` Konstrukt nicht auf den parallelen Bereich gebunden.

```
void f()
{
  int i = 1;
  #pragma omp parallel sections
  {
    #pragma omp section
    {
      #pragma omp critical (name)
      {
        #pragma omp parallel
        {
          #pragma omp single
          {
            i++;
          }
        }
      }
    }
  }
}
```