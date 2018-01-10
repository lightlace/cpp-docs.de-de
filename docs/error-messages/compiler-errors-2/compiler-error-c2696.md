---
title: Compilerfehler Fehler C2696 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2696
dev_langs: C++
helpviewer_keywords: C2696
ms.assetid: 6c6eb7df-1230-4346-9a73-abf14c20785d
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e4d6efbf8dcf10d1608bb1a54b843a49d42cb22a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2696"></a>Compilerfehler Fehler C2696
Ein temporäres Objekt von einem verwalteten Typ 'Typ' kann nicht erstellt werden.  
  
Verweise auf `const` in einem nicht verwalteten Programm bewirken, dass der Compiler den Konstruktor aus, und erstellen ein temporäres Objekt auf dem Stapel. Eine verwaltete Klasse kann jedoch nie auf dem Stapel erstellt werden.  
  
C2696 ist nur über die veraltete Compileroption erreichbar **/CLR: oldSyntax**.  
