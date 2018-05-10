---
title: A.29 Verwendung der Arbeit Freigabe erstellt innerhalb einer critical-Konstrukt | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: d5c8a83f-2f51-4f23-8ddf-d267e347507f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ccbb39a9067adf545339d02fe0c05e24fbcdb0a4
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
---
# <a name="a29---use-of-work-sharing-constructs-inside-a-critical-construct"></a>A.29   Verwenden von Arbeitsteilungskonstrukten innerhalb eines critical-Konstrukts
Das folgende Beispiel veranschaulicht die Verwendung eines Konstrukts Freigeben von Arbeit in einem `critical` erstellen. In diesem Beispiel ist kompatibel, da die Arbeit Freigabe zu erstellen und die `critical` Konstrukt nicht zur selben parallele Region gebunden.  
  
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