---
title: Compilerfehler C3552 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3552
dev_langs:
- C++
helpviewer_keywords:
- C3552
ms.assetid: 83401524-1bf1-44c0-8aca-a6eb35c4224c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a5f1453a6175019ad7c90471330d11c77da26134
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3552"></a>Compilerfehler C3552
"Typname": Ein spät angegebener Rückgabetyp darf nicht "auto" enthalten.  
  
 Wenn Sie das `auto` -Schlüsselwort als Platzhalter für den Rückgabetyp einer Funktion verwenden, müssen Sie einen spät angegebenen Rückgabetyp angeben. Allerdings können Sie kein weiteres `auto` -Schlüsselwort verwenden, um den spät angegebenen Rückgabetyp anzugeben. Im folgenden Codefragment wird beispielsweise der Fehler C3552 verursacht.  
  
 `auto myFunction->auto; // C3552`