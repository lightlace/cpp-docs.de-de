---
title: Neuverteilen von Komponenten mit Mergemodulen | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- merge modules, using
- redistributing applications, using merge modules
ms.assetid: 93b84211-bf9b-4a78-9f22-474ac2ef7840
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 093c732563844b14a3f99662150d4db9b2fac1fb
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="redistributing-components-by-using-merge-modules"></a>Neuverteilen von Komponenten mit Mergemodulen
Visual Studio enthält [Mergemodule](http://msdn.microsoft.com/library/aa367434) für jede Visual C++-Komponente, die dafür lizenziert ist, um mit einer Anwendung weiter verteilt zu werden. Wenn ein Mergemodul in einer Windows Installer-Setupdatei kompiliert wird, aktiviert es die Bereitstellung von spezifischen DLLs für Computer, die eine spezifische Plattform haben. Geben Sie in der Setupdatei an, dass die Mergemodule erforderliche Komponenten für Ihre Anwendung sind. Wenn Visual Studio installiert ist, werden die Mergemodule \Programme\Gemeinsame dateien\mergemodule\-Module installiert\\. (Nur nicht-Debugversionen der Visual C++-DLLs können verteilt werden.) Weitere Informationen und einen Link auf eine Liste von Mergemodulen, die für die weiterverteilung lizenziert sind, finden Sie unter [Neuverteilen von Visual C++-Dateien](../ide/redistributing-visual-cpp-files.md).  
  
 Mergemodule können Sie die Installation des weitervertreibbaren Visual C++-DLLs im Ordner "%SYSTEMROOT%\system32\" aktivieren. (Visual Studio selbst verwendet dieses Verfahren.) Die Installation in diesen Ordner ist jedoch nur erfolgreich, wenn der installierende Benutzer über Administratorrechte verfügt.  
  
 Wir empfehlen, dass Sie Mergemodule nicht verwenden, außer wenn Sie Ihre Anwendung nicht bedienen müssen und Sie keine Abhängigkeiten von mehr als einer Version der DLLs haben. Mergemodule für unterschiedliche Versionen derselben DLL können nicht in einen Installer einbezogen werden, und Mergemodule erschweren es, dass DLLs unabhängig von Ihrer Anwendung bedient werden. Stattdessen empfehlen wir, dass Sie ein Visual C++ Redistributable Package installieren.  
  
## <a name="see-also"></a>Siehe auch  
 [Verteilen von Visual C++-Dateien](../ide/redistributing-visual-cpp-files.md)