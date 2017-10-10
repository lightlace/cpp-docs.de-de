---
title: Compilerfehler Fehler C2097 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2097
dev_langs:
- C++
helpviewer_keywords:
- C2097
ms.assetid: 7e5b2fd4-f61c-4b8a-b265-93e987a04bd3
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: d6955a610e3109c3b16edf96913be4503ee4c647
ms.contentlocale: de-de
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2097"></a>Compilerfehler Fehler C2097
Unzulässige Initialisierung  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>Dieser Fehler kann eine der folgenden Ursachen haben:  
  
1.  Die Initialisierung einer Variablen mit einem nicht konstanten Wert.  
  
2.  Die Initialisierung eine kurze Adresse mit einer long-Adresse.  
  
3.  Die Initialisierung eines lokalen Struktur, Union oder Array mit einem nicht konstanten Ausdruck beim Kompilieren mit **"/ Za"**.  
  
4.  Die Initialisierung mit einem Ausdruck mit einem Kommaoperator.  
  
5.  Die Initialisierung mit einem Ausdruck, der weder konstant noch symbolische ist.
