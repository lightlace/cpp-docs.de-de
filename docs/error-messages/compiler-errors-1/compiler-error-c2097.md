---
title: Compilerfehler Fehler C2097 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2097
dev_langs:
- C++
helpviewer_keywords:
- C2097
ms.assetid: 7e5b2fd4-f61c-4b8a-b265-93e987a04bd3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fa4b867c7f043d796f208fdc7100509893147daf
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2097"></a>Compilerfehler Fehler C2097
Unzulässige Initialisierung  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>Dieser Fehler kann eine der folgenden Ursachen haben:  
  
1.  Die Initialisierung einer Variablen mit einem nicht konstanten Wert.  
  
2.  Die Initialisierung eine kurze Adresse mit einer long-Adresse.  
  
3.  Die Initialisierung eines lokalen Struktur, Union oder Array mit einem nicht konstanten Ausdruck beim Kompilieren mit **"/ Za"**.  
  
4.  Die Initialisierung mit einem Ausdruck mit einem Kommaoperator.  
  
5.  Die Initialisierung mit einem Ausdruck, der weder konstant noch symbolische ist.