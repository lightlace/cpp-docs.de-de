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
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e50154d88a5019cdc181c4921c09cbd222d8b530
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2097"></a>Compilerfehler Fehler C2097
Unzulässige Initialisierung  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>Dieser Fehler kann eine der folgenden Ursachen haben:  
  
1.  Die Initialisierung einer Variablen mit einem nicht konstanten Wert.  
  
2.  Die Initialisierung eine kurze Adresse mit einer long-Adresse.  
  
3.  Die Initialisierung eines lokalen Struktur, Union oder Array mit einem nicht konstanten Ausdruck beim Kompilieren mit **"/ Za"**.  
  
4.  Die Initialisierung mit einem Ausdruck mit einem Kommaoperator.  
  
5.  Die Initialisierung mit einem Ausdruck, der weder konstant noch symbolische ist.