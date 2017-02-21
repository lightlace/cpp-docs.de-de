---
title: "Neuverteilen von Komponenten mit Mergemodulen | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Mergemodule, Verwenden"
  - "Verteilen von Anwendungen, Verwenden von Mergemodulen"
ms.assetid: 93b84211-bf9b-4a78-9f22-474ac2ef7840
caps.latest.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 21
---
# Neuverteilen von Komponenten mit Mergemodulen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] umfasst [Mergemodule](http://msdn.microsoft.com/library/aa367434) für jede [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)]\-Komponente, die dafür lizenziert ist, mit einer Anwendung weiter verteilt zu werden.  Wenn ein Mergemodul in einer Windows Installer\-Setupdatei kompiliert wird, aktiviert es die Bereitstellung von spezifischen DLLs für Computer, die eine spezifische Plattform haben.  Geben Sie in der Setupdatei an, dass die Mergemodule erforderliche Komponenten für Ihre Anwendung sind.  Wenn [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] installiert wird, werden die Mergemodule unter „\\Programme\\Gemeinsame Dateien\\Mergemodule\\“ installiert. \(Keine Debugversionen von [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)]\-DLLs dürfen verteilt werden.\) Weitere Informationen und einen Link zu einer Liste von Mergemodulen, die für die Neuverteilung lizenziert sind, finden Sie unter [Verteilen von Visual C\+\+\-Dateien](../ide/redistributing-visual-cpp-files.md).  
  
 Mithilfe der Mergemodule können Sie die Installation von neu verteilbaren [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] DLLs in den Ordner „%SYSTEMROOT%\\system32\\“ aktivieren. \([!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] selbst verwendet dieses Verfahren.\) Die Installation in diesen Ordner ist jedoch nur erfolgreich, wenn der installierende Benutzer über Administratorrechte verfügt.  
  
 Wir empfehlen, dass Sie Mergemodule nicht verwenden, außer wenn Sie Ihre Anwendung nicht bedienen müssen und sie keine Abhängigkeiten von mehr als einer Version der DLLs haben.  Mergemodule für unterschiedliche Versionen derselben DLL können nicht in einen Installer einbezogen werden, und Mergemodule erschweren es, dass DLLs unabhängig von Ihrer Anwendung bedient werden.  Statt dessen wird es empfohlen, dass Sie ein neu verteilbares [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)]\-Paket installieren.  
  
## Siehe auch  
 [Verteilen von Visual C\+\+\-Dateien](../ide/redistributing-visual-cpp-files.md)