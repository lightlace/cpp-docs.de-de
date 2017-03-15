---
title: "Erstellen von parallelen C/C++-Assemblys"
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
  - "Parallele Anwendungen [C++]"
ms.assetid: 7fa20b16-3737-4f76-a0b5-1dacea19a1e8
caps.latest.revision: 18
caps.handback.revision: "13"
ms.author: "corob"
manager: "ghogen"
---
# Erstellen von parallelen C/C++-Assemblys
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Eine [parallele Assembly](_win32_side_by_side_assemblies) ist eine Auflistung von Ressourcen, z. B. eine Gruppe von DLLs, Windows\-Klassen, COM\-Servern, Typbibliotheken oder Schnittstellen, die einer Anwendung zur Laufzeit zur Verfügung stehen.  Der Hauptvorteil des erneuten Verpackens von DLLs in Assemblys besteht darin, dass Anwendungen verschiedene Versionen einer Assembly gleichzeitig verwenden und die aktuell installierten Assemblys im Falle der Freigabe einer aktualisierten Version gewartet werden können.  
  
 Eine Visual C\+\+\-Anwendung verwendet möglicherweise in verschiedenen Teilen der Anwendung eine oder mehrere DLLs.  Zur Laufzeit werden die DLLs in den Hauptprozess geladen, und der erforderliche Code wird ausgeführt.  Die Anwendung ist auf das Betriebssystem angewiesen, um die angeforderten DLLs zu finden, weitere abhängige DLLs zu erkennen und diese anschließend zusammen mit der angeforderten DLL zu laden.  Unter Versionen des Windows\-Betriebssystems vor Windows XP, Windows Server 2003 und Windows Vista sucht das Ladeprogramm des Betriebssystems entweder im lokalen Anwendungsordner oder in einem anderen, im Systempfad angegebenen Ordner nach abhängigen DLLs.  Unter Windows XP, Windows Server 2003 und Windows Vista kann das Ladeprogramm des Betriebssystems auch mithilfe einer [Manifestdatei](http://msdn.microsoft.com/library/aa375365) nach abhängigen DLLs sowie nach parallelen Assemblys suchen, die diese DLLs enthalten.  
  
 Wenn eine DLL mit Visual Studio erstellt wird, verfügt sie standardmäßig über ein [Anwendungsmanifest](http://msdn.microsoft.com/library/aa374191), das als RT\_MANIFEST\-Ressource mit der ID 2 eingebettet ist.  Genau wie bei einer ausführbaren Datei beschreibt dieses Manifest die Abhängigkeiten dieser DLL von anderen Assemblys.  Dies setzt voraus, dass die DLL nicht Bestandteil einer parallelen Assembly ist und dass von dieser DLL abhängige Anwendungen zum Laden der DLL kein Anwendungsmanifest verwenden, sondern stattdessen darauf warten, dass das Ladeprogramm des Betriebssystems diese DLL im Systempfad findet.  
  
> [!NOTE]
>  Wenn eine DLL ein Anwendungsmanifest verwendet, muss das Manifest unbedingt als Ressource mit einer ID gleich 2 eingebettet sein.  Beim dynamischen Laden der DLL zur Laufzeit \(z. B. mit der [LoadLibrary](http://msdn.microsoft.com/library/windows/desktop/ms684175)\-Funktion\) lädt das Ladeprogramm des Betriebssystems die im Manifest der DLL angegebenen abhängigen Assemblys.  Ein externes Anwendungsmanifest für DLLs wird bei einem `LoadLibrary`\-Aufruf nicht überprüft.  Wenn das Manifest nicht eingebettet ist, lädt das Ladeprogramm möglicherweise falsche Versionen von Assemblys, oder es kann die abhängigen Assemblys nicht finden.  
  
 Eine oder mehrere DLLs, die miteinander in Beziehung stehen, können in einer parallelen Assembly mit einem entsprechenden [Assemblymanifest](http://msdn.microsoft.com/library/aa374219) neu verpackt werden. Dieses Assemblymanifest beschreibt, aus welchen Dateien die Assembly besteht und von welchen anderen parallelen Assemblys sie abhängig ist.  
  
> [!NOTE]
>  Wenn eine Assembly eine DLL enthält, empfiehlt es sich, das Assemblymanifest als Ressource mit der ID 1 in diese DLL einzubetten. Die private Assembly kann denselben Namen wie die DLL erhalten.  Lautet der Name der DLL mylibrary.dll ist, kann der Wert des name\-Attributs, das im assemblyIdentity \<Element\> des Manifests verwendet wird, auch mylibrary.  In den Fällen, in denen eine Bibliothek über eine andere Erweiterung als .dll verfügt \(z. B. erstellt ein MFC\-ActiveX\-Steuerelementprojekt eine OCX\-Bibliothek\), kann ein externes Manifest erstellt werden.  In diesem Fall muss sich der Name der Assembly und ihres Manifests vom Namen der DLL unterscheiden \(z. B. MyAssembly, MyAssembly.manifest und mylibrary.ocx\).  Es wird jedoch empfohlen, derartigen Bibliotheken per Umbenennung die Erweiterung .dll zu verleihen und das Manifest als Ressource einzubetten, um die zukünftigen Wartungskosten für diese Assembly zu reduzieren.  Weitere Informationen darüber, wie das Betriebssystem nach privaten Assemblys sucht, finden Sie unter [Assemblysuchsequenz](http://msdn.microsoft.com/library/aa374224).  
  
 Diese Änderung erlaubt möglicherweise die Bereitstellung der entsprechenden DLLs als [private Assembly](_win32_private_assemblies) im lokalen Anwendungsordner oder als [freigegebene Assembly](https://msdn.microsoft.com/en-us/library/aa375996.aspx) im WinSxS\-Assemblycache.  Um das korrekte Laufzeitverhalten dieser neuen Assembly zu erreichen, müssen verschiedene Schritte ausgeführt werden, die in [Richtlinien für das Erstellen von parallelen Assemblys](http://msdn.microsoft.com/library/aa375155) beschrieben werden.  Nachdem eine Assembly ordnungsgemäß erstellt wurde, kann sie entweder als freigegebene oder als private Assembly zusammen mit der Anwendung bereitgestellt werden, die von dieser Assembly abhängig ist.  Beim Installieren paralleler Assemblys als freigegebene Assemblys kann der Ersteller entweder den in [Installieren von Win32\-Assemblys für die parallele Freigabe unter Windows XP](http://msdn.microsoft.com/library/aa369532) beschriebenen Richtlinien folgen oder [Mergemodule](http://msdn.microsoft.com/library/aa369820) verwenden.  Beim Installieren paralleler Assemblys als private Assembly können Sie einfach die entsprechende DLL, die Ressourcen und das Assemblymanifest als Teil des Installationsvorgangs in den lokalen Anwendungsordner auf dem Zielcomputer kopieren. Dadurch wird sichergestellt, dass das Ladeprogramm diese Assembly zur Laufzeit findet \(siehe [Assemblysuchsequenz](http://msdn.microsoft.com/library/aa374224)\).  Eine andere Methode besteht darin, [Windows Installer](http://msdn.microsoft.com/library/cc185688) zu verwenden und die in [Installieren von Win32\-Assemblys für die private Nutzung einer Anwendung unter Windows XP](http://msdn.microsoft.com/library/aa369534) beschriebenen Richtlinien zu befolgen.  
  
## Siehe auch  
 [Bereitstellungsbeispiele](../ide/deployment-examples.md)   
 [Erstellen isolierter C\/C\+\+\-Anwendungen](../build/building-c-cpp-isolated-applications.md)   
 [Erstellen von isolierten Anwendungen und parallelen Assemblys \(C\/C\+\+\)](../build/building-c-cpp-isolated-applications-and-side-by-side-assemblies.md)