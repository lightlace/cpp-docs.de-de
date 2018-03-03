---
title: Manifestgenerierung in Visual Studio | Microsoft Docs
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
- manifests [C++]
ms.assetid: 0af60aa9-d223-42cd-8426-b3fc543a2a81
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3d701d73103ee2c5ac72eb36d9919132f0578b1b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="manifest-generation-in-visual-studio"></a>Manifestgenerierung in Visual Studio
Die Generierung einer Manifestdatei für ein bestimmtes Projekt kann gesteuert werden, in das Projekt **Eigenschaftenseiten** Dialogfeld. Auf der **Konfigurationseigenschaften** auf **Linker**, klicken Sie dann **Manifestdatei**, klicken Sie dann **Manifest generieren**. Standardmäßig werden die Projekteigenschaften des neuen Projekten festgelegt, eine Manifestdatei generiert. Jedoch ist es möglich, deaktivieren Sie die Generierung des Manifests für ein Projekt mit der **Manifest generieren** -Eigenschaft des Projekts. Wenn diese Eigenschaft festgelegt wird, um **Ja**, das Manifest für dieses Projekt generiert wird. Andernfalls der vom Linker ignoriert Assemblyinformationen beim Auflösen der Abhängigkeiten des Anwendungscodes, und nicht das Manifest zu generieren.  
  
 Das Buildsystem von Visual Studio ermöglicht das Manifest in die endgültige Binärdatei der Anwendung-Datei eingebettet oder als externe Datei generiert werden. Dieses Verhalten wird gesteuert, indem Sie die **Manifest einbetten** -Option in der **Projekteigenschaften** Dialogfeld. Öffnen Sie zum Festlegen dieser Eigenschaft die **Manifesttool** Knoten, wählen Sie dann **ein- und Ausgabe**. Wenn das Manifest nicht eingebettet ist, wird er als externe Datei generiert und im selben Verzeichnis wie die endgültige Binärdatei gespeichert. Wenn das Manifest eingebettet wird, bettet Visual Studio die endgültigen Manifeste mit dem folgenden Prozess:  
  
1.  Nachdem Sie der Quellcode in Objektdateien kompiliert wird, erfasst der Linker zur abhängigen Assembly an. Beim Verknüpfen der endgültigen Binärdatei, generiert der Linker ein intermediate Manifest, das später verwendet wird, um die endgültige Manifest zu generieren.  
  
2.  Nachdem die Zwischendateien Produktmanifest und verknüpfen fertig gestellt wurden, werden Manifesttool zum Zusammenführen einer endgültigen Manifest, und speichern Sie sie als externe Datei ausgeführt.  
  
3.  Das Projekt Buildsystem und erkennt, ob das Manifest generiert, die für die Manifesttool unterschiedliche Informationen als die bereits in die Binärdatei eingebettetes Manifest enthält.  
  
4.  Wenn das Manifest in die Binärdatei eingebettet unterscheidet sich von das Manifest von Manifesttool generiert oder die Binärdatei kein eingebettetes Manifest enthält, Visual Studio wird aufrufen den Linker ein weiteres Mal die externe Manifestdatei als in die Binärdatei eingebettet ein die Ressource.  
  
5.  Wenn das Manifest in die Binärdatei eingebettet das Manifest generiert, die für die Manifesttool identisch ist, wird der Build auf dem nächsten Schritt fortgesetzt.  
  
 Das Manifest in die endgültige Binärdatei als Text Ressource eingebettet ist, und es kann angezeigt werden, indem Sie die endgültige Binärdatei als Datei in Visual Studio öffnen. Um sicherzustellen, dass das Manifest mit den richtigen Bibliotheken verweist, befolgen Sie die Schritte in [Grundlegendes zu den Abhängigkeiten einer Visual C++-Anwendung](../ide/understanding-the-dependencies-of-a-visual-cpp-application.md) oder führen Sie die Vorschläge in beschriebenen der [Problembehandlung](../build/troubleshooting-c-cpp-isolated-applications-and-side-by-side-assemblies.md) Abschnitt.  
  
## <a name="see-also"></a>Siehe auch  
 [Vorgehensweise: Einbetten eines Manifests in einer C/C++-Anwendung](../build/how-to-embed-a-manifest-inside-a-c-cpp-application.md)   
 [Informationen zu privaten Assemblys](http://msdn.microsoft.com/library/ff951638)   
 [Manifesttool](http://msdn.microsoft.com/library/aa375649)   
 [Manifestgenerierung für C/C++-Programme](../build/understanding-manifest-generation-for-c-cpp-programs.md)