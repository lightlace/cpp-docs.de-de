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
ms.openlocfilehash: 70ccaf34a0191f0bd69c95d2cb110f6e6542a6d1
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2696"></a>Compilerfehler Fehler C2696
Ein temporäres Objekt von einem verwalteten Typ 'Typ' kann nicht erstellt werden.  
  
Verweise auf `const` in einem nicht verwalteten Programm bewirken, dass der Compiler den Konstruktor aus, und erstellen ein temporäres Objekt auf dem Stapel. Eine verwaltete Klasse kann jedoch nie auf dem Stapel erstellt werden.  
  
C2696 ist nur über die veraltete Compileroption erreichbar **/CLR: oldSyntax**.  
