---
title: Arbeiten mit Importbibliotheken und Exportdateien | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- LIB [C++], /DEF option
- import libraries
- LIB [C++], import libraries and export files
- export files
- import libraries, creating
ms.assetid: d8175596-9773-4c2f-959d-b05b065a5161
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9e0d60eed00abc60c09e03838a113c424d8f173a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="working-with-import-libraries-and-export-files"></a>Arbeiten mit Importbibliotheken und Exportdateien
LIB können mit der DEF-Option Sie um eine Importbibliothek und einer Exportdatei zu erstellen. LINK verwendet, die die Exportdatei ein Programm erstellen, enthält exportiert (in der Regel eine Dynamic Link Library (DLL)), und die Importbibliothek verwendet, um Verweise auf diese Exporte in anderen Programmen zu beheben.  
  
 Beachten Sie, dass wenn Sie die Importbibliothek in einem vorherigen Schritt erstellen, bevor Sie die DLL-Datei erstellen, den gleichen Satz von Objektdateien müssen beim Erstellen der DLL übergeben werden wie bei der Erstellung der Importbibliothek her.  
  
 In den meisten Fällen müssen Sie keine LIB verwenden, um die Importbibliothek zu erstellen. Wenn Sie ein Programm (eine ausführbare Datei oder DLL), das Exporte enthält verknüpfen, erstellt LINK automatisch eine Importbibliothek, die die Exporte beschreibt. Wenn Sie ein Programm, die diese Exporte verweist verknüpfen, geben Sie später der Importbibliothek her.  
  
 Jedoch, wenn eine DLL mit einem Programm exportiert werden, die es auch importiert, gibt an, ob direkt oder indirekt LIB können Importbibliotheken erstellen. Beim Erstellen eine Importbibliothek LIB erstellt wird auch eine Exportdatei erstellt. Wenn eine DLL verknüpfen, müssen Sie die Exportdatei verwenden.  
  
## <a name="see-also"></a>Siehe auch  
 [LIB-Referenz](../../build/reference/lib-reference.md)