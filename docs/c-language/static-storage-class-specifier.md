---
title: static-Speicherklassenspezifizierer | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- static variables, specifier
- storage classes, static
- static storage class specifiers
ms.assetid: 9bce361e-919b-46b9-8148-40d7ab0eb024
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c957b78eeb506e9f1f91a670cf5cc4d52ad72878
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="static-storage-class-specifier"></a>static-Speicherklassenspezifizierer
Eine Variable, die auf interner Ebene mit dem **static**-Speicherklassenspezifizierer deklariert wurde, hat eine globale Lebensdauer, wird jedoch nur innerhalb des Blocks angezeigt, in dem sie deklariert ist. Bei konstanten Zeichenfolgen ist die Verwendung von **static** nützlich, da es den Mehraufwand einer häufigen Initialisierung in häufig aufgerufenen Funktionen verringert.  
  
## <a name="remarks"></a>Hinweise  
Wenn Sie nicht explizit eine **static**-Variable initialisieren, wird sie standardmäßig mit 0 (null) initialisiert. Innerhalb einer Funktion bewirkt **static**, dass Speicher zugeordnet wird, und dient als Definition. Interne statische Variablen stellen privaten Festspeicher bereit, der nur für eine einzelne Funktion sichtbar ist.  
  
## <a name="see-also"></a>Siehe auch  
[C-Speicherklassen](c-storage-classes.md)  
[Speicherklassen (C++)](../cpp/storage-classes-cpp.md)  