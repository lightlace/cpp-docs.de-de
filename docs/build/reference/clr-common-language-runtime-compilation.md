---
title: /clr (Common Language Runtime-Kompilierung)
ms.date: 05/16/2019
f1_keywords:
- /CLR
- VC.Project.VCNMakeTool.CompileAsManaged
- VC.Project.VCCLCompilerTool.CompileAsManaged
helpviewer_keywords:
- cl.exe compiler, common language runtime option
- -clr compiler option [C++]
- clr compiler option [C++]
- /clr compiler option [C++]
- Managed Extensions for C++, compiling
- common language runtime, /clr compiler option
ms.assetid: fec5a8c0-40ec-484c-a213-8dec918c1d6c
ms.openlocfilehash: fa2be3d3ce17df104cda121e4869c975ec6dd440
ms.sourcegitcommit: a10c9390413978d36b8096b684d5ed4cf1553bc8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/17/2019
ms.locfileid: "65837309"
---
# <a name="clr-common-language-runtime-compilation"></a>/clr (Common Language Runtime-Kompilierung)

Ermöglicht Anwendungen und Komponenten, Funktionen aus der Common Language Runtime (CLR) zu verwenden.

## <a name="syntax"></a>Syntax

> **/clr**[ **:** _options_]

## <a name="arguments"></a>Argumente

*options*<br/>
Einer oder mehrere der folgenden Schalter, durch Komma getrennt.

- Keine

   Ohne Optionen erstellt **/clr** Metadaten für die Anwendung. Die Metadaten können von anderen CLR-Anwendungen genutzt werden, und ermöglichen, dass eine Anwendung Typen und Daten in den Metadaten anderer CLR-Komponenten nutzt. Weitere Informationen finden Sie unter [Gemischte (native und verwaltete) Assemblys](../../dotnet/mixed-native-and-managed-assemblies.md).

- **pure**

   **/clr:pure ist veraltet**. Die Option wurde in Visual Studio 2017 und höher entfernt. Es wird empfohlen, dass Sie Code, der reines MSIL sein muss, nach C# portieren.

- **safe**

   **/clr:safe ist veraltet**. Die Option wurde in Visual Studio 2017 und höher entfernt. Es wird empfohlen, dass Sie Code, der sicheres MSIL sein muss, nach C# portieren.

- **noAssembly**

   **/clr:noAssembly ist veraltet**. Verwenden Sie stattdessen [/LN (Create MSIL Module)](ln-create-msil-module.md) .

   Legt fest, dass ein Assemblymanifest nicht in die Ausgabedatei eingefügt wird. Standardmäßig ist die **noAssembly** -Option nicht wirksam.

   Ein verwaltetes Programm, das keine Assemblymetadaten im Manifest aufweist, wird als ein *Modul*bezeichnet. Die **noAssembly** -Option kann nur zum Erzeugen eines Moduls verwendet werden. Wenn Sie bei der Kompilierung [/c](c-compile-without-linking.md) und **/clr:noAssembly**verwenden, geben Sie die Option [/NOASSEMBLY](noassembly-create-a-msil-module.md) in der Linkerphase ein, um ein Modul zu erstellen.

   Vor Visual Studio 2005 war bei Verwendung von **/clr:noAssembly** die Angabe von **/LD**erforderlich. **/LD** ist jetzt bei der Angabe von **/clr:noAssembly**impliziert.

- **initialAppDomain**

   Ermöglicht, dass eine Visual C++-Anwendung mit Version 1 von CLR ausgeführt wird.  Eine Anwendung, die mit **initialAppDomain** kompiliert wurde, sollte nicht mit einer Anwendung verwendet werden, die ASP.NET verwendet, da Version 1 von CLR die Unterstützung hierfür fehlt.

- **nostdlib**

   Weist den Compiler an, das Standardverzeichnis für \clr zu ignorieren. Der Compiler erzeugt Fehler, wenn Sie mehrere Versionen einer DLL wie „System.dll“ einschließen. Mit dieser Option können Sie angeben, welches Framework während der Kompilierung verwendet wird.

## <a name="remarks"></a>Anmerkungen

Verwalteter Code ist Code, der überprüft und von der CLR verwaltet werden kann. Verwalteter Code kann auf verwaltete Objekte zugreifen. Weitere Informationen finden Sie unter [/clr Restrictions](clr-restrictions.md).

Informationen zum Entwickeln von Anwendungen, die verwaltete Typen definieren und verwenden, finden Sie unter [Component Extensions for Runtime Platforms](../../extensions/component-extensions-for-runtime-platforms.md).

Eine mithilfe von **/clr** kompilierte Anwendung kann verwaltete Daten enthalten.

Informationen zum Aktivieren des Debuggens einer verwalteten Anwendung finden Sie unter [/ASSEMBLYDEBUG (DebuggableAttribute hinzufügen)](assemblydebug-add-debuggableattribute.md).

Auf dem Heap der Garbage Collection werden nur CLR-Typen instanziiert. Weitere Informationen finden Sie unter [Klassen und Strukturen](../../extensions/classes-and-structs-cpp-component-extensions.md). Um eine Funktion in systemeigenem Code zu kompilieren, verwenden Sie das `unmanaged` -Pragma. Weitere Informationen finden Sie unter [verwaltet, nicht verwaltet](../../preprocessor/managed-unmanaged.md).

In der Standardeinstellung ist **/clr** nicht aktiv. Wenn **/clr** aktiviert ist, ist auch **/MD** aktiv. Weitere Informationen finden Sie unter [/MD, /MT, /LD (Laufzeitbibliothek verwenden)](md-mt-ld-use-run-time-library.md). **/MD** stellt sicher, dass die dynamisch verknüpften Multithread-Versionen der Laufzeitroutinen aus den standardmäßigen Headerdateien (. h) ausgewählt werden. Multithreading ist für die verwaltete Programmierung erforderlich, da der CLR-Garbage Collector Finalizer in einem Hilfsthread ausführt.

Wenn Sie mithilfe von **/c**kompilieren, können Sie den CLR-Typ der generierten Ausgabedatei mit [/CLRIMAGETYPE](clrimagetype-specify-type-of-clr-image.md)angeben.

**/clr** impliziert **/EHa**, und keine anderen **/EH** -Optionen werden für **/clr**unterstützt. Weitere Informationen finden Sie unter [/EH (Ausnahmebehandlungsmodell)](eh-exception-handling-model.md).

Weitere Informationen zum Bestimmen des CLR-Imagetyps einer Datei finden Sie unter [/CLRHEADER](clrheader.md).

Alle an einen bestimmten Aufruf des Linkers übergebenen Module müssen mit derselben Compileroption für die Laufzeitbibliothek kompiliert werden ( **/MD** oder **/LD**).

Verwenden Sie die [/ASSEMBLYRESOURCE](assemblyresource-embed-a-managed-resource.md) -Linkeroption, um eine Ressource in eine Assembly einzubetten. Mit den Linkeroptionen[/DELAYSIGN](delaysign-partially-sign-an-assembly.md), [/KEYCONTAINER](keycontainer-specify-a-key-container-to-sign-an-assembly.md)und [/KEYFILE](keyfile-specify-key-or-key-pair-to-sign-an-assembly.md) können Sie auch anpassen, wie eine Assembly erstellt wird.

Wenn **/clr** verwendet wird, ist das `_MANAGED` -Symbol mit 1 definiert. Weitere Informationen finden Sie unter [Predefined Macros](../../preprocessor/predefined-macros.md).

Die globalen Variablen in einer systemeigenen Objektdatei werden zuerst initialisiert (während DllMain, wenn die ausführbare Datei eine DLL ist), und anschließend werden die globalen Variablen im verwalteten Abschnitt initialisiert (bevor verwalteter Code ausgeführt wird). `#pragma` [Init_seg](../../preprocessor/init-seg.md) wirkt sich nur auf die Reihenfolge der Initialisierung in den verwalteten und nicht verwalteten Kategorien aus.

## <a name="metadata-and-unnamed-classes"></a>Metadaten und unbenannte Klassen

Unbenannte Klassen erscheinen in Metadaten mit folgendem Namen: `$UnnamedClass$`*crc-of-current-file-name*`$`*index*`$`, wobei *index* eine sequenzieller Zähler für die unbenannten Klassen in der Kompilierung ist. Im folgenden Codebeispiel wird z. B. eine unbenannte Klasse in den Metadaten generiert.

```cpp
// clr_unnamed_class.cpp
// compile by using: /clr /LD
class {} x;
```

Mithilfe von ildasm.exe können Sie Metadaten anzeigen.

## <a name="see-also"></a>Siehe auch

[MSVC-Compileroptionen](compiler-options.md)<br/>
[Syntax für die MSVC-Compilerbefehlszeile](compiler-command-line-syntax.md)
