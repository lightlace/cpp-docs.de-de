---
title: "Manifestgenerierung in Visual&#160;Studio"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Manifeste [C++]"
ms.assetid: 0af60aa9-d223-42cd-8426-b3fc543a2a81
caps.latest.revision: 14
caps.handback.revision: "14"
ms.author: "corob"
manager: "ghogen"
---
# Manifestgenerierung in Visual&#160;Studio
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Generierung einer Manifestdatei für ein bestimmtes Projekt wird mithilfe des Dialogfelds **Eigenschaftenseiten** des Projekts gesteuert.  Klicken Sie auf der Registerkarte **Konfigurationseigenschaften** auf die Option **Linker**, dann auf **Manifestdatei** und anschließend auf **Manifest generieren**.  Standardmäßig werden die Projekteigenschaften neuer Projekte so festgelegt, dass eine Manifestdatei generiert wird.  Die Generierung eines Manifests für ein Projekt kann jedoch über die Projekteigenschaft **Manifest generieren** deaktiviert werden.  Wenn diese Eigenschaft auf **Ja** festgelegt ist, wird das Manifest für dieses Projekt generiert.  Andernfalls ignoriert der Linker die Assemblyinformationen beim Auflösen der Abhängigkeiten des Anwendungscodes und generiert kein Manifest.  
  
 Das Buildsystem von Visual Studio erlaubt sowohl die Einbettung des Manifests in die endgültige Binärdatei der Anwendung als auch die Generierung als externe Datei.  Dieses Verhalten wird von der Option **Manifest einbetten** im Dialogfeld **Projekteigenschaften** gesteuert.  Öffnen Sie zum Festlegen dieser Eigenschaft den Knoten **Manifesttool**, und wählen Sie dann die Option **Eingabe und Ausgabe** aus.  Wenn das Manifest nicht eingebettet wird, wird es als externe Datei generiert und in demselben Verzeichnis wie die endgültige Binärdatei gespeichert.  Wenn das Manifest eingebettet wird, bettet Visual Studio die endgültigen Manifeste mithilfe des folgenden Prozesses ein:  
  
1.  Nach dem Kompilieren des Quellcodes zu Objektdateien sammelt der Linker Informationen zu abhängigen Assemblys.  Während des Linkens der endgültigen Binärdatei generiert der Linker ein Zwischenmanifest, das zur späteren Generierung des endgültigen Manifests dient.  
  
2.  Nachdem die Generierung des Zwischenmanifests und das Linken abgeschlossen sind, wird das Manifesttool ausgeführt, das das endgültige Manifest zusammenführt und in einer externen Datei speichert.  
  
3.  Anschließend überprüft das Projektbuildsystem, ob das vom Manifesttool generierte Manifest Informationen enthält, die von dem bereits in der Binärdatei eingebetteten Manifest abweichen.  
  
4.  Wenn sich das in der Binärdatei eingebettete Manifest von dem Manifest unterscheidet, das vom Manifesttool generiert wurde, oder wenn die Binärdatei kein eingebettetes Manifest enthält, ruft Visual Studio den Linker ein weiteres Mal auf, um die externe Manifestdatei als Ressource in die Binärdatei einzubetten.  
  
5.  Wenn sich das in der Binärdatei eingebettete Manifest nicht von dem Manifest unterscheidet, das vom Manifesttool generiert wurde, wird der Buildvorgang mit dem nächsten Schritt fortgesetzt.  
  
 Das Manifest wird als Textressource in die endgültige Binärdatei eingebettet. Es kann durch Öffnen der endgültigen Binärdatei in Visual Studio als Datei angezeigt werden.  Um sicherzustellen, dass das Manifest auf die richtigen Bibliotheken zeigt, folgen Sie den in [Grundlegendes zu den Abhängigkeiten einer Visual C\+\+\-Anwendung](../ide/understanding-the-dependencies-of-a-visual-cpp-application.md) beschriebenen Anweisungen, oder befolgen Sie die Vorschläge im Abschnitt [Problembehandlung](../build/troubleshooting-c-cpp-isolated-applications-and-side-by-side-assemblies.md).  
  
## Siehe auch  
 [Gewusst wie: Einbetten eines Manifests in eine C\/C\+\+\-Anwendung](../build/how-to-embed-a-manifest-inside-a-c-cpp-application.md)   
 [Private Assemblys](_win32_private_assemblies)   
 [Manifesttool](http://msdn.microsoft.com/library/aa375649)   
 [Manifestgenerierung für C\/C\+\+\-Programme](../build/understanding-manifest-generation-for-c-cpp-programs.md)