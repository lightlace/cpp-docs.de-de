---
title: Compiler-Fehler C2696 | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2696
dev_langs:
- C++
helpviewer_keywords:
- C2696
ms.assetid: 6c6eb7df-1230-4346-9a73-abf14c20785d
caps.latest.revision: 12
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: c243063a9770542f137d5950e8a269f771960f74
ms.openlocfilehash: 08b8a7990efbf981aec342b99bbb558fd9fab8d5
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c2696"></a>Compiler-Fehler C2696
Ein temporäres Objekt eines verwalteten Typs 'Typ' kann nicht erstellt werden.  
  
Verweise auf `const` in einem nicht verwalteten Programm bewirken, dass der Compiler den Konstruktor aufzurufen, und erstellen ein temporäres Objekt auf dem Stapel. Eine verwaltete Klasse kann jedoch nie auf dem Stapel erstellt werden.  
  
C2696 ist nur über die veralteten Compileroption erreichbar **/CLR: oldSyntax**.  

