---
title: -Clr (Common Language Runtime-Kompilierung) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /CLR
- VC.Project.VCNMakeTool.CompileAsManaged
- VC.Project.VCCLCompilerTool.CompileAsManaged
dev_langs:
- C++
helpviewer_keywords:
- cl.exe compiler, common language runtime option
- -clr compiler option [C++]
- clr compiler option [C++]
- /clr compiler option [C++]
- Managed Extensions for C++, compiling
- common language runtime, /clr compiler option
ms.assetid: fec5a8c0-40ec-484c-a213-8dec918c1d6c
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a754e6c2fd8c709fd0397a2c0f78a7385819c586
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2018
---
# <a name="clr-common-language-runtime-compilation"></a>/clr (Common Language Runtime-Kompilierung)
Ermöglicht Anwendungen und Komponenten, Funktionen aus der Common Language Runtime (CLR) zu verwenden.  
  
## <a name="syntax"></a>Syntax  
  
```  
/clr[:options]  
```  
  
## <a name="arguments"></a>Argumente  
 `options`  
 Einer oder mehrere der folgenden Schalter, durch Komma getrennt.  
  
 **/clr**  
 Erstellt Metadaten für die Anwendung. Die Metadaten können von anderen CLR-Anwendungen genutzt werden, und ermöglichen, dass eine Anwendung Typen und Daten in den Metadaten anderer CLR-Komponenten nutzt.  
  
 Weitere Informationen finden Sie unter  
  
 [Gemischte (systemeigene und verwaltete) Assemblys](../../dotnet/mixed-native-and-managed-assemblies.md) und  
  
 [How to: Migrate to /clr](../../dotnet/how-to-migrate-to-clr.md).  
  
 **/clr:pure**  
 /clr:pure ist veraltet. Diese Option wird von einer zukünftigen Version des Compilers möglicherweise nicht unterstützt. Es wird empfohlen, dass Sie Code, der reines MSIL sein muss, nach C# portieren.  
  
 **/clr:safe**  
 /clr:safe ist veraltet. Diese Option wird von einer zukünftigen Version des Compilers möglicherweise nicht unterstützt. Es wird empfohlen, dass Sie Code portieren, die sichere MSIL in c# sein müssen. 
  
 **/clr:noAssembly**  
 Legt fest, dass ein Assemblymanifest nicht in die Ausgabedatei eingefügt wird. Standardmäßig ist die **noAssembly** -Option nicht wirksam.  
  
 Die **NoAssembly** -Option ist veraltet. Verwenden Sie stattdessen [/LN (Create MSIL Module)](../../build/reference/ln-create-msil-module.md) .  
  
 Ein verwaltetes Programm, das keine Assemblymetadaten im Manifest aufweist, wird als ein *Modul*bezeichnet. Die **noAssembly** -Option kann nur zum Erzeugen eines Moduls verwendet werden. Wenn Sie bei der Kompilierung [/c](../../build/reference/c-compile-without-linking.md) und **/clr:noAssembly**verwenden, geben Sie die Option [/NOASSEMBLY](../../build/reference/noassembly-create-a-msil-module.md) in der Linkerphase ein, um ein Modul zu erstellen.  
  
 Vor Visual C++ 2005 war bei Verwendung von **/clr:noAssembly** die Angabe von **/LD**erforderlich. **/LD** ist jetzt bei der Angabe von **/clr:noAssembly**impliziert.  
  
 **/clr:initialAppDomain**  
 Ermöglicht, dass eine [!INCLUDE[vcprvc](../../build/includes/vcprvc_md.md)] -Anwendung mit Version 1 von CLR ausgeführt wird. Bei Verwendung von **InitialAppDomain**, und klicken Sie dann einige Probleme auftreten, die in beschriebenen [Fehler: AppDomainUnloaded-Ausnahme bei Verwendung verwalteter Erweiterungen für Visual C++-Komponenten](http://go.microsoft.com/fwlink/p/?linkid=169465) auf Microsoft Support-Website.  
  
 Eine Anwendung, die mit **initialAppDomain** kompiliert wurde, sollte nicht mit einer Anwendung verwendet werden, die ASP.NET verwendet, da Version 1 von CLR die Unterstützung hierfür fehlt.  
  
 **/clr:nostdlib**  
 Weist den Compiler an, das Standardverzeichnis für \clr zu ignorieren. Der Compiler erzeugt Fehler, wenn Sie mehrere Versionen einer DLL wie „System.dll“ einschließen. Mit dieser Option können Sie angeben, welches Framework während der Kompilierung verwendet wird.  
  
## <a name="remarks"></a>Hinweise  
 Verwalteter Code ist Code, der überprüft und von der CLR verwaltet werden kann. Verwalteter Code kann auf verwaltete Objekte zugreifen. Weitere Informationen finden Sie unter [/clr Restrictions](../../build/reference/clr-restrictions.md).  
  
 Informationen zum Entwickeln von Anwendungen, die verwaltete Typen definieren und verwenden, finden Sie unter [Component Extensions for Runtime Platforms](../../windows/component-extensions-for-runtime-platforms.md).  
  
 Eine mithilfe von **/clr** kompilierte Anwendung kann verwaltete Daten enthalten.  
  
 Zum Aktivieren des Debuggens einer verwalteten Anwendung finden Sie unter [/ASSEMBLYDEBUG (DebuggableAttribute hinzufügen)](../../build/reference/assemblydebug-add-debuggableattribute.md).  
  
 Auf dem Heap der Garbage Collection werden nur CLR-Typen instanziiert. Weitere Informationen finden Sie unter [Klassen und Strukturen](../../windows/classes-and-structs-cpp-component-extensions.md). Um eine Funktion in systemeigenem Code zu kompilieren, verwenden Sie das `unmanaged` -Pragma. Weitere Informationen finden Sie unter [verwaltete, unverwaltete](../../preprocessor/managed-unmanaged.md).  
  
 In der Standardeinstellung ist **/clr** nicht aktiv. Wenn **/clr** aktiviert ist, ist auch **/MD** aktiv. Weitere Informationen finden Sie unter [/MD, /MT, /LD (Laufzeitbibliothek verwenden)](../../build/reference/md-mt-ld-use-run-time-library.md). **/MD** stellt sicher, dass die dynamisch verknüpften Multithread-Versionen der Laufzeitroutinen aus den standardmäßigen Headerdateien (. h) ausgewählt werden. Multithreading ist für die verwaltete Programmierung erforderlich, da der CLR-Garbage Collector Finalizer in einem Hilfsthread ausführt.  
  
 Wenn Sie bei der Kompilierung **/c**, können Sie angeben, die CLR-Typ der generierten Ausgabedatei mit [/CLRIMAGETYPE](../../build/reference/clrimagetype-specify-type-of-clr-image.md).  
  
 **/clr** impliziert **/EHa**, und keine anderen **/EH** -Optionen werden für **/clr**unterstützt. Weitere Informationen finden Sie unter [/EH (Ausnahmebehandlungsmodell)](../../build/reference/eh-exception-handling-model.md).  
  
 Weitere Informationen zum Bestimmen des CLR-Imagetyps einer Datei finden Sie unter [/CLRHEADER](../../build/reference/clrheader.md).  
  
 Alle an einen bestimmten Aufruf des Linkers übergebenen Module müssen mit derselben Compileroption für die Laufzeitbibliothek kompiliert werden (**/MD** oder **/LD**).  
  
 Verwenden Sie die [/ASSEMBLYRESOURCE](../../build/reference/assemblyresource-embed-a-managed-resource.md) -Linkeroption, um eine Ressource in eine Assembly einzubetten. Mit den Linkeroptionen[/DELAYSIGN](../../build/reference/delaysign-partially-sign-an-assembly.md), [/KEYCONTAINER](../../build/reference/keycontainer-specify-a-key-container-to-sign-an-assembly.md)und [/KEYFILE](../../build/reference/keyfile-specify-key-or-key-pair-to-sign-an-assembly.md) können Sie auch anpassen, wie eine Assembly erstellt wird.  
  
 Wenn **/clr** verwendet wird, ist das `_MANAGED` -Symbol mit 1 definiert. Weitere Informationen finden Sie unter [Predefined Macros](../../preprocessor/predefined-macros.md).  
  
 Die globalen Variablen in einer systemeigenen Objektdatei werden zuerst initialisiert (während DllMain, wenn die ausführbare Datei eine DLL ist), und anschließend werden die globalen Variablen im verwalteten Abschnitt initialisiert (bevor verwalteter Code ausgeführt wird). `#pragma`[Init_seg](../../preprocessor/init-seg.md) wirkt sich nur auf die Reihenfolge der Initialisierung in den verwalteten und nicht verwalteten Kategorien.  
  
## <a name="metadata-and-unnamed-classes"></a>Metadaten und unbenannte Klassen  
 Unbenannte Klassen erscheinen in Metadaten mit folgendem Namen: `$UnnamedClass$`*crc-of-current-file-name*`$`*index*`$`, wobei *index* eine sequenzieller Zähler für die unbenannten Klassen in der Kompilierung ist. Im folgenden Codebeispiel wird z. B. eine unbenannte Klasse in den Metadaten generiert.  
  
```  
// clr_unnamed_class.cpp  
// compile by using: /clr /LD  
class {} x;  
```  
  
 Mithilfe von ildasm.exe können Sie Metadaten anzeigen.  
  
## <a name="managed-extensions-for-c"></a>Verwaltete Erweiterungen für C++  
 Visual C++ unterstützt nicht mehr die Option **/clr:oldsyntax** . Diese Option ist seit Visual Studio 2005 veraltet. Die unterstützte Syntax zum Schreiben von verwaltetem Code in C++ ist C++/CLI. Weitere Informationen finden Sie unter [Component Extensions for Runtime Platforms](../../windows/component-extensions-for-runtime-platforms.md).  
  
 Wenn Sie Code mit Managed Extensions für C++ verwenden, ist es ratsam, ihn zu portieren, damit Sie die C++/CLI-Syntax verwenden können. Informationen zum Portieren von Code finden Sie unter [C++/CLI Migration Primer](../../dotnet/cpp-cli-migration-primer.md).  
  
#### <a name="to-set-this-compiler-option-in-visual-studio"></a>So legen Sie diese Compileroption in Visual Studio fest  
  
1.  Klicken Sie im **Projektmappen-Explorer**mit der rechten Maustaste auf den Projektnamen, und wählen Sie **Eigenschaften** aus, um das Dialogfeld **Eigenschaftenseiten** für das Projekt zu öffnen.  
  
2.  Wählen Sie den Ordner **Konfigurationseigenschaften** aus.  
  
3.  Ändern Sie auf der Eigenschaftenseite **Allgemein** die Eigenschaft **Common Language Runtime-Unterstützung** .  
  
    > [!NOTE]
    >  Wenn **/clr** im Dialogfeld **Eigenschaftenseiten** aktiviert ist, werden Eigenschaften der Compileroptionen, die nicht mit **/clr** kompatibel sind, bei Bedarf ebenfalls angepasst. Wenn beispielsweise **/RTC** festgelegt und dann **/clr** aktiviert wird, wird **/RTC** deaktiviert.  
    >   
    >  Legen Sie beim Debuggen einer **/clr** -Anwendung außerdem die Eigenschaft **Debuggertyp** auf **Gemischt** oder **Nur verwaltet**fest. Weitere Informationen finden Sie unter [Projekteinstellungen für eine C++-Debugkonfiguration](/visualstudio/debugger/project-settings-for-a-cpp-debug-configuration).  
  
     Informationen zum Erstellen eines Moduls finden Sie unter [/NOASSEMBLY (Erstellen eines MSIL-Moduls)](../../build/reference/noassembly-create-a-msil-module.md).  
  
#### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.CompileAsManaged%2A>.  
  
## <a name="see-also"></a>Siehe auch  
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)