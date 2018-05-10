---
title: 2.2 bedingte Kompilierung | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 8f9c914d-736c-48cf-899d-c8029dbe1e32
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b3d8c7073548c015d9982b721387176a0ca658c2
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
---
# <a name="22-conditional-compilation"></a>2.2 Bedingte Kompilierung
Die _**OPENMP** Makroname wird durch OpenMP-kompatible Implementierung definiert, als der dezimalen Konstante *Yyyymm*, der Jahr und Monat der genehmigten Spezifikation ist. Dieses Makro muss das Subjekt einer **#define** oder ein **#undef** -präprozessanweisung.  
  
```  
#ifdef _OPENMP  
iam = omp_get_thread_num() + index;  
#endif  
```  
  
 Wenn Lieferanten Erweiterungen mit OpenMP definieren, können sie zusätzliche vordefinierte Makros angeben.