---
title: Neuverteilen von Komponenten mit Mergemodulen | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- merge modules, using
- redistributing applications, using merge modules
ms.assetid: 93b84211-bf9b-4a78-9f22-474ac2ef7840
caps.latest.revision: "21"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 14eb80452a9b5ceefeea7ff204c42288b7542c5a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="redistributing-components-by-using-merge-modules"></a>Neuverteilen von Komponenten mit Mergemodulen
Visual Studio enthält [Mergemodule](http://msdn.microsoft.com/library/aa367434) für jede Visual C++-Komponente, die dafür lizenziert ist, um mit einer Anwendung weiter verteilt zu werden. Wenn ein Mergemodul in einer Windows Installer-Setupdatei kompiliert wird, aktiviert es die Bereitstellung von spezifischen DLLs für Computer, die eine spezifische Plattform haben. Geben Sie in der Setupdatei an, dass die Mergemodule erforderliche Komponenten für Ihre Anwendung sind. Wenn Visual Studio installiert ist, werden die Mergemodule \Programme\Gemeinsame dateien\mergemodule\-Module installiert\\. (Nur nicht-Debugversionen der Visual C++-DLLs können verteilt werden.) Weitere Informationen und einen Link auf eine Liste von Mergemodulen, die für die weiterverteilung lizenziert sind, finden Sie unter [Neuverteilen von Visual C++-Dateien](../ide/redistributing-visual-cpp-files.md).  
  
 Mergemodule können Sie die Installation des weitervertreibbaren Visual C++-DLLs im Ordner "%SYSTEMROOT%\system32\" aktivieren. (Visual Studio selbst verwendet dieses Verfahren.) Die Installation in diesen Ordner ist jedoch nur erfolgreich, wenn der installierende Benutzer über Administratorrechte verfügt.  
  
 Wir empfehlen, dass Sie Mergemodule nicht verwenden, außer wenn Sie Ihre Anwendung nicht bedienen müssen und sie keine Abhängigkeiten von mehr als einer Version der DLLs haben. Mergemodule für unterschiedliche Versionen derselben DLL können nicht in einen Installer einbezogen werden, und Mergemodule erschweren es, dass DLLs unabhängig von Ihrer Anwendung bedient werden. Stattdessen empfehlen wir, dass Sie ein Visual C++ Redistributable Package installieren.  
  
## <a name="see-also"></a>Siehe auch  
 [Verteilen von Visual C++-Dateien](../ide/redistributing-visual-cpp-files.md)