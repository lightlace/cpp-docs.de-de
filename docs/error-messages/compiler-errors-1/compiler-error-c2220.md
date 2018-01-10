---
title: Compilerfehler C2220 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2220
dev_langs: C++
helpviewer_keywords: C2220
ms.assetid: d610802c-64d7-40ad-a2a6-0ed0b6815a6c
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 14da9ea0905f2aa7aa67c2b7524314a4af74246b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2220"></a>Compilerfehler C2220
Warnung als Fehler behandelt - keine Objektdatei generiert  
  
 [/ WX](../../build/reference/compiler-option-warning-level.md) teilt dem Compiler mit, alle Warnungen als Fehler behandelt werden sollen. Da ein Fehler aufgetreten ist, wurde kein Objekt und keine ausführbare Datei generiert.  
  
 Dieser Fehler wird nur angezeigt, wenn die **/WX** Flag festgelegt ist und eine Warnung auftritt, während der Kompilierung. Um diesen Fehler zu beheben, müssen Sie jede Warnung im Projekt ausschließen.  
  
### <a name="to-fix-use-one-of-the-following-techniques"></a>So beheben Sie den Fehler mit einer der folgenden Methoden  
  
-   Korrigieren Sie die Probleme, die Warnungen im Projekt verursachen.  
  
-   Kompilieren Sie auf einer niedrigeren Warnungsebene – verwenden Sie z. B. **/W3** anstelle von **/W4**.  
  
-   Verwenden einer [Warnung](../../preprocessor/warning.md) Pragma deaktivieren oder eine bestimmte Warnung zu unterdrücken.  
  
-   Verwenden Sie keine **/WX** kompiliert.