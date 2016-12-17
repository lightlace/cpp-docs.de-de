---
title: "Problembehandlung bei isolierten Anwendungen und parallelen Assemblys (C/C++)"
ms.custom: na
ms.date: "12/15/2016"
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
  - "Problembehandlung bei isolierten Anwendungen"
  - "Problembehandlung bei parallelen Assemblys"
  - "Problembehandlung in Visual C++"
ms.assetid: 3257257a-1f0b-4ede-8564-9277a7113a35
caps.latest.revision: 28
caps.handback.revision: "28"
ms.author: "corob"
manager: "ghogen"
---
# Problembehandlung bei isolierten Anwendungen und parallelen Assemblys (C/C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Beim Laden einer C\/C\+\+\-Anwendung kann ein Fehler auftreten, wenn abhängige Bibliotheken nicht gefunden werden.  In diesem Artikel werden einige häufige Ursachen für Fehler beim Laden einer C\/C\+\+\-Anwendung beschrieben und Schritte zur Lösung des jeweiligen Problems vorgeschlagen.  
  
 Wenn eine Anwendung nicht geladen wird, da in ihrem Manifest eine Abhängigkeit zu einer parallelen Assembly angegeben ist und diese Assembly weder als private Assembly im selben Ordner wie die ausführbare Datei noch im systemeigenen Assemblycache im Ordner "%WINDIR%\\WinSxS\\" installiert wurde, kann – abhängig von der Windows\-Version, auf der Sie die Anwendung auszuführen versuchen – eine der folgenden Fehlermeldungen angezeigt werden.  
  
-   Die Anwendung konnte nicht richtig initialisiert werden \(0xc0000135\).  
  
-   Diese Anwendung konnte aufgrund einer falschen Anwendungskonfiguration nicht gestartet werden.  Installieren Sie die Anwendung neu, um das Problem zu beheben.  
  
-   Das angegebene Programm kann nicht ausgeführt werden.  
  
 Wenn die Anwendung über kein Manifest verfügt und von einer DLL abhängig ist, die von Windows nicht an den typischen Speicherorten gefunden werden kann, wird möglicherweise eine Fehlermeldung wie die folgende angezeigt:  
  
-   Diese Anwendung konnte nicht gestartet werden, da *eine erforderliche DLL\-Datei* nicht gefunden wurde.  Neuinstallation der Anwendung könnte das Problem beheben.  
  
 Wenn eine Anwendung, die auf einem Computer bereitgestellt wird, auf dem Visual Studio nicht installiert ist, abstürzt und dabei Fehlermeldungen ähnlich der oben genannten angezeigt werden, überprüfen Sie folgende Aspekte:  
  
1.  Befolgen Sie die unter [Grundlegendes zu den Abhängigkeiten einer Visual C\+\+\-Anwendung](../ide/understanding-the-dependencies-of-a-visual-cpp-application.md) beschriebenen Schritte.  Der Dependency Walker zeigt den größten Teil der Abhängigkeiten für eine Anwendung oder DLL an.  Wenn Sie feststellen, dass einige DLLs fehlen, installieren Sie diese DLLs auf dem Computer, auf dem Sie die Anwendung ausführen möchten.  
  
2.  Das Ladeprogramm des Betriebssystems verwendet das Anwendungsmanifest zum Laden von Assemblys, von denen die Anwendung abhängig ist.  Das Manifest kann entweder als Ressource in die Binärdatei eingebettet oder als separate Datei im lokalen Anwendungsordner gespeichert sein.  Um zu überprüfen, ob das Manifest in die Binärdatei eingebettet ist, öffnen Sie die Binärdatei in [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)], und durchsuchen Sie die Ressourcenliste darin nach RT\_MANIFEST.  Wenn Sie kein eingebettetes Manifest finden, suchen Sie im Anwendungsordner nach einer Datei mit einem Namen wie "\<Name\_der\_Binärdatei\>.\<Erweiterung\>.manifest".  
  
3.  Wenn die Anwendung von parallelen Assemblys abhängig ist und kein Manifest vorhanden ist, müssen Sie sicherstellen, dass der Linker ein Manifest für das Projekt generiert.  Dazu müssen Sie die Linkeroption **Manifest generieren** im Dialogfeld **Projekteigenschaften** des Projekts aktivieren.  
  
4.  Wenn das Manifest in die Binärdatei eingebettet ist, stellen Sie sicher, dass die ID von RT\_MANIFEST für diesen Typ von Binärdatei korrekt ist.  Weitere Informationen über die zu verwendende Ressourcen\-ID finden Sie unter [Verwenden von parallelen Assemblys als Ressource \(Windows\)](http://msdn.microsoft.com/library/windows/desktop/aa376617.aspx).  Wenn sich das Manifest in einer separaten Datei befindet, öffnen Sie es in einem XML\- oder Text\-Editor.  Weitere Informationen zu Manifesten und Regeln für die Bereitstellung finden Sie unter [Manifeste](http://msdn.microsoft.com/library/aa375365).  
  
    > [!NOTE]
    >  Wenn sowohl ein eingebettetes Manifest als auch eine separate Manifestdatei vorhanden sind, verwendet das Ladeprogramm des Betriebssystems das eingebettete Manifest und ignoriert die separate Datei.  Unter Windows XP trifft allerdings das Gegenteil zu – die separate Manifestdatei wird verwendet und das eingebettete Manifest ignoriert.  
  
5.  Es empfiehlt sich, ein Manifest in jede DLL\-Datei einzubetten, da externe Manifeste ignoriert werden, wenn eine DLL durch einen `LoadLibrary`\-Aufruf geladen wird.  Weitere Informationen dazu finden Sie unter [Assemblymanifeste](http://msdn.microsoft.com/library/aa374219).  
  
6.  Stellen Sie sicher, dass alle im Manifest aufgelisteten Assemblys ordnungsgemäß auf dem Computer installiert sind.  Für jede Assembly wird im Manifest der Name, die Versionsnummer und die Prozessorarchitektur angegeben.  Wenn die Anwendung von parallelen Assemblys abhängig ist, stellen Sie sicher, dass diese Assemblys ordnungsgemäß auf dem Computer installiert sind, sodass sie vom Ladeprogramm des Betriebssystems gefunden werden können, wie in [Assemblysuchsequenz](http://msdn.microsoft.com/library/aa374224) beschrieben.  Denken Sie daran, dass 64\-Bit\-Assemblys nicht in 32\-Bit\-Prozessen geladen und unter 32\-Bit\-Betriebssystemen nicht ausgeführt werden können.  
  
## Beispiel  
 Angenommen, die Anwendung APPL.EXE wurde mit [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] erstellt.  Das Anwendungsmanifest ist entweder als Binärressource RT\_MANIFEST, die eine ID gleich 1 hat, in APPL.EXE eingebettet, oder es ist als separate Datei "appl.exe.manifest" gespeichert.  Der Inhalt des Manifests kann ungefähr so aussehen:  
  
```  
<assembly xmlns="urn:schemas-microsoft-com:asm.v1" manifestVersion="1.0">  
  <dependency>  
    <dependentAssembly>  
      <assemblyIdentity type="win32" name="Fabrikam.SxS.Library" version="2.0.20121.0" processorArchitecture="x86" publicKeyToken="1fc8b3b9a1e18e3e"></assemblyIdentity>  
    </dependentAssembly>  
  </dependency>  
</assembly>  
```  
  
 Dieses Manifest teilt dem Ladeprogramm des Betriebssystems mit, dass APPL.EXE von einer Assembly mit dem Namen Fabrikam.SxS.Library, Version 2.0.20121.0, abhängig ist, die für die 32\-Bit\-x86\-Prozessorarchitektur erstellt wurde.  Die abhängige parallele Assembly kann entweder als freigegebene Assembly oder als private Assembly installiert werden.  
  
 Das Manifest einer freigegebenen parallelen Assembly wird im Ordner "%WINDIR%\\WinSxS\\Manifests\\" installiert.  Es identifiziert die Assembly und listet deren Inhalt auf, also die DLLs, die Teil dieser Assembly sind:  
  
```  
<?xml version="1.0" encoding="UTF-8" standalone="yes"?>  
<assembly xmlns="urn:schemas-microsoft-com:asm.v1" manifestVersion="1.0">  
   <noInheritable/>  
   <assemblyIdentity type="win32" name="Fabrikam.SxS.Library" version="2.0.20121.0" processorArchitecture="x86" publicKeyToken="1fc8b3b9a1e18e3e"/>  
   <file name="Fabrikam.Main.dll" hash="3ca5156e8212449db6c622c3d10f37d9adb1ab12" hashalg="SHA1"/>  
   <file name="Fabrikam.Helper.dll" hash="92cf8a9bb066aea821d324ca4695c69e55b2d1c2" hashalg="SHA1"/>  
</assembly>  
```  
  
 Parallele Assemblys können auch [Herausgeberkonfigurationsdateien](http://msdn.microsoft.com/library/aa375682) verwenden \(auch Richtliniendateien genannt\), um Anwendungen und Assemblys global umzuleiten, damit sie eine Version einer Assembly anstatt einer anderen Version derselben Assembly verwenden.  Sie können die Richtlinien für eine freigegebene Assembly im Ordner "%WINDIR%\\WinSxS\\Policies\\" überprüfen.  Hier ein Beispiel für eine Richtliniendatei:  
  
```  
<?xml version="1.0" encoding="UTF-8" standalone="yes"?>  
<assembly xmlns="urn:schemas-microsoft-com:asm.v1" manifestVersion="1.0">  
  
   <assemblyIdentity type="win32-policy" name="policy.2.0.Fabrikam.SxS.Library" version="2.0.20121.0" processorArchitecture="x86" publicKeyToken="1fc8b3b9a1e18e3e"/>  
   <dependency>  
      <dependentAssembly>  
         <assemblyIdentity type="win32" name="Fabrikam.SxS.Library" processorArchitecture="x86" publicKeyToken="1fc8b3b9a1e18e3e"/>  
         <bindingRedirect oldVersion="2.0.10000.0-2.0.20120.99" newVersion="2.0.20121.0"/>  
      </dependentAssembly>  
   </dependency>  
</assembly>  
```  
  
 Diese Richtliniendatei gibt an, dass jede Anwendung oder Assembly, die Version 2.0.10000.0 dieser Assembly anfordert, stattdessen Version 2.0.20121.0 verwenden soll. Dies ist die aktuelle, auf dem System installierte Version.  Wenn eine Version der Assembly, die im Manifest der Anwendung enthalten ist, in der Richtliniendatei angegeben ist, sucht das Ladeprogramm im Ordner "%WINDIR%\\WinSxS\\" nach einer Version dieser im Manifest angegebenen Assembly. Wenn diese Version nicht installiert ist, schlägt das Laden fehl.  Und wenn die Assemblyversion 2.0.20121.0 nicht installiert ist, schlägt das Laden von Anwendungen fehl, die die Version 2.0.10000.0 anfordern.  
  
 Die Assembly kann jedoch auch als private parallele Assembly im installierten Anwendungsordner installiert werden.  Wenn das Betriebssystem die Assembly nicht als freigegebene Assembly finden kann, wird die Assembly als private Assembly gesucht. Dabei gilt folgende Reihenfolge:  
  
1.  Im lokalen Ordner der Anwendung wird nach einer Manifestdatei mit dem Namen "\<Assemblyname\>.manifest" gesucht.  In diesem Beispiel sucht das Ladeprogramm in demselben Ordner nach "Fabrikam.SxS.Library.manifest", in dem sich APPL.EXE befindet.  Wenn das Manifest gefunden wird, lädt das Ladeprogramm die Assembly aus dem Anwendungsordner.  Wenn die Assembly nicht gefunden wird, schlägt das Laden fehl.  
  
2.  Versuchen Sie, den Ordner "\\\<Assemblyname\>\\" in dem Ordner zu öffnen, der APPL.EXE enthält. Wenn "\\\<Assemblyname\>\\" vorhanden ist, versuchen Sie eine Manifestdatei aus diesem Ordner zu laden, die den Namen "\<Assemblyname\>.manifest" hat.  Wenn das Manifest gefunden wird, lädt das Ladeprogramm die Assembly aus dem Ordner "\\\<Assemblyname\>\\ ".  Wenn die Assembly nicht gefunden wird, schlägt das Laden fehl.  
  
 Weitere Informationen darüber, wie das Ladeprogramm nach abhängigen Assemblys sucht, finden Sie unter [Assemblysuchsequenz](http://msdn.microsoft.com/library/aa374224).  Wenn das Ladeprogramm eine abhängige Assembly nicht als private Assembly finden kann, schlägt das Laden fehl, und es wird die Meldung "Das angegebene Programm kann nicht ausgeführt werden" angezeigt.  Um diesen Fehler zu beheben, müssen Sie sicherstellen, dass abhängige Assemblys – und DLLs, die Teil dieser Assemblys sind – entweder als private oder als freigegebene Assemblys auf dem Computer installiert werden.  
  
## Siehe auch  
 [Konzept der isolierten Anwendungen und der parallelen Assemblys](../build/concepts-of-isolated-applications-and-side-by-side-assemblies.md)   
 [Erstellen von isolierten Anwendungen und parallelen Assemblys \(C\/C\+\+\)](../build/building-c-cpp-isolated-applications-and-side-by-side-assemblies.md)