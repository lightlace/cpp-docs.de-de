---
title: Compilerfehler Fehler C2696 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2696
dev_langs:
- C++
helpviewer_keywords:
- C2696
ms.assetid: 6c6eb7df-1230-4346-9a73-abf14c20785d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 65ccdd6d2c8c34c360811b80d5a93abe76f5ef8e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33235038"
---
# <a name="compiler-error-c2696"></a>Compilerfehler Fehler C2696
Ein temporäres Objekt von einem verwalteten Typ 'Typ' kann nicht erstellt werden.  
  
Verweise auf `const` in einem nicht verwalteten Programm bewirken, dass der Compiler den Konstruktor aus, und erstellen ein temporäres Objekt auf dem Stapel. Eine verwaltete Klasse kann jedoch nie auf dem Stapel erstellt werden.  
  
C2696 ist nur über die veraltete Compileroption erreichbar **/CLR: oldSyntax**.  
