---
title: Compilerwarnung (Stufe 1) C4025 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C4025
dev_langs: C++
helpviewer_keywords: C4025
ms.assetid: c4f6a651-0641-4446-973e-8290065e49ad
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 07bb6db07baed9ce191ed396177c73cf7d3fa2ed
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4025"></a>Compilerwarnung (Stufe 1) C4025
"Anzahl": Zeiger auf ein separates Segment an Funktion mit variablen Argumenten übergeben: Parameteranzahl  
  
 Die Übergabe eines basierten Zeigers an eine Funktion mit variablen Argumenten bewirkt, dass der Zeiger normalisiert wird. Dies kann unvorhersehbare Folgen haben. Übergeben Sie keine basierten Zeiger an Funktionen mit variablen Argumenten.