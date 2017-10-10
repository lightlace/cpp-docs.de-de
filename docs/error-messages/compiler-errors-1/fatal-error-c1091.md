---
title: Schwerwiegender Fehler C1091 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C1091
dev_langs:
- C++
helpviewer_keywords:
- C1091
ms.assetid: 812d4201-9154-48b0-b9af-5959c082ca33
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 6c3fd2dae1f3258ce90d30c78792c498be75615a
ms.contentlocale: de-de
ms.lasthandoff: 10/09/2017

---
# <a name="fatal-error-c1091"></a>Schwerwiegender Fehler C1091
Compilerlimit: Die Zeichenfolge überschreitet die Länge um "Länge" Bytes.  
  
 Eine Zeichenfolgekonstante hat die aktuelle Grenze für die Länge von Zeichenfolgen überschritten.  
  
 Teilen Sie ggf. die statische Zeichenfolge in zwei (oder mehr) Variablen auf und verwenden Sie [strcpy_s](../../c-runtime-library/reference/strcpy-s-wcscpy-s-mbscpy-s.md) , um das Ergebnis im Rahmen der Deklaration oder während der Laufzeit zusammenzuführen.
