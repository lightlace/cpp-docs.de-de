---
title: Mathematischer Fehler M6203 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- M6203
dev_langs:
- C++
helpviewer_keywords:
- M6203
ms.assetid: bd7fdd1c-83e4-4d6a-901e-10a0308bf5be
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7660284f9e5e69b53f3289eaa1aa424944bbecb4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33319311"
---
# <a name="math-error-m6203"></a>Mathematischer Fehler M6203
'Funktion': _OVERFLOW-Fehler  
  
 Das Ergebnis der angegebenen Funktion war zu groß für dargestellt werden.  
  
 Dieser Fehler-Ruft die `_matherr` -Funktion mit den Namen der Funktion, die Argumente und den Fehlertyp. Sie können Umschreiben der `_matherr` Funktion, um die Behandlung bestimmter Gleitkommaoperationen zur Laufzeit anzupassen.