---
title: Schwerwiegender Fehler C1210 | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C1210
dev_langs:
- C++
helpviewer_keywords:
- C1210
ms.assetid: e2208309-c284-425c-a7e8-48e96e66f35b
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: cc82b83860786ffc3f0aee73ede18ecadef16a7a
ms.openlocfilehash: f3abd56aebdf7e83bbab10b6083ad6fc14987fbd
ms.lasthandoff: 02/24/2017

---
# <a name="fatal-error-c1210"></a>Schwerwiegender Fehler C1210
/clr:pure und /clr:safe werden von der installierten Laufzeitversion nicht unterstützt.  
  
 Die **/CLR: pure** und **/CLR: safe** Compileroptionen in Visual Studio 2015 veraltet sind.  
  
 C1210 tritt auf, wenn Sie einen Compiler der aktuellen Version, aber eine Common Language Runtime (CLR) einer früheren Version verwenden.  
  
 Bestimmte Funktionen des Compilers funktionieren möglicherweise nicht in einer früheren Version der Laufzeit.  
  
 Installieren Sie die CLR-Version, die für die Verwendung mit dem Compiler vorgesehen ist, um den Fehler C1210 zu beheben.
