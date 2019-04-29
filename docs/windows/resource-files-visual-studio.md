---
title: Ressourcendateien (C++)
ms.date: 02/14/2019
f1_keywords:
- vc.editors.resource
helpviewer_keywords:
- resources [C++]
- .rc files [C++]
- resource files [C++]
- resource script files [C++]
- resource script files [C++], Win-32 based applications
- resource script files [C++], files updated when editing resources
- resources [C++], types of resource files
- rct files [C++]
- rc files [C++]
- resource files [C++], types of
- .rct files [C++]
- resource script files [C++], unsupported types
- manifest resources [C++]
- resources [C++], manifest
- resources [C++], opening
- file types [C++], for resources
- resources [C++], editing
- files [C++], editable types
- resource editing
ms.assetid: 4d2b6fcc-07cf-4289-be87-83a60f69533c
ms.openlocfilehash: 45db6d0139cfa3aa8a2eaa8fe6d18158cb6646ce
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62387915"
---
# <a name="resource-files-c"></a>Ressourcendateien (C++)

> [!NOTE]
> Da Projekte in .NET-Programmiersprachen keine Ressourcenskriptdateien verwenden, müssen Sie Ihre Ressourcen im **Projektmappen-Explorer**. Verwenden der [bildbearbeitung](../windows/image-editor-for-icons.md) und [binär-Editor](binary-editor.md) , Bearbeitung von Ressourcendateien in verwalteten Projekten möglich.
>
> Bei den zu bearbeitenden verwalteten Ressourcen muss es sich um verknüpfte Ressourcen handeln. Das Bearbeiten eingebetteter Ressourcen wird von den Visual Studio-Ressourcen-Editoren nicht unterstützt.

Der Begriff *Ressourcendatei* können auf eine Anzahl von Dateitypen, z. B. verweisen:

- Die Ressourcenskriptdatei (RC) eines Programms.

- Eine Ressourcenvorlagendatei (RCT).

- Eine einzelne Ressource als eigenständige Datei. Dieser Typ enthält eine Bitmap, Symbole oder Cursor-Datei, die von einer RC-Datei bezeichnet wird.

- Ein von der Entwicklungsumgebung generierte Headerdatei. Diese Typen fallen `Resource.h`, die von einer RC-Datei bezeichnet wird.

Ressourcen finden Sie in andere Dateitypen wie z. B. .exe, DLL und RES-Dateien als bezeichnet *Ressourcen*.

Sie können mit arbeiten *Ressourcendateien* und *Ressourcen* von innerhalb des Projekts. Sie können auch mit Anwendungen arbeiten, die nicht Teil des aktuellen Projekts sind oder außerhalb der Entwicklungsumgebung von Visual Studio erstellt wurden. Sie haben unter anderem folgende Möglichkeiten:

- Arbeiten mit geschachtelten und bedingt eingeschlossenen Ressourcendateien.

- Aktualisieren von vorhandenen Ressourcen, oder sie in Visual C++ zu konvertieren.

- Importieren oder Exportieren grafischer Ressourcendateien in die oder aus der aktuelle(n) Ressourcendatei.

- Einschließen gemeinsam verwendeter oder schreibgeschützter Bezeichner (Symbole), die von der Entwicklungsumgebung nicht geändert werden können.

- Schließen Sie Ressourcen in Ihre ausführbaren Dateien (.exe)-Datei, die nicht erforderlich, bearbeiten (oder darf nicht bearbeitet werden kann), z. B. freigegebene Ressourcen von mehreren Projekten ein.

- Einschließen von Ressourcentypen, die von der Entwicklungsumgebung nicht unterstützt werden.

Weitere Informationen zu Ressourcen finden Sie unter Vorgehensweise [Ressourcen erstellen](../windows/how-to-create-a-resource-script-file.md), [Ressourcen verwalten](../windows/how-to-copy-resources.md), und [sind Ressourcen zur Kompilierungszeit](../windows/how-to-include-resources-at-compile-time.md).

## <a name="editable-resources"></a>Bearbeitbaren Ressourcen

Um die darin enthaltenen Ressourcen zu bearbeiten, können die folgenden Typen von Dateien geöffnet werden:

| Dateiname | Beschreibung |
|---|---|
| .rc | Ressourcenskriptdateien |
| .rct | Ressourcenvorlagendateien |
| .res | Ressourcendateien |
| .resx | Verwaltete Ressourcendateien |
| .exe | Ausführbare Dateien |
| .dll | Dynamic Link Library-Dateien |
| .bmp, .ico, .dib und .cur | Bitmap, Symbol, Symbolleiste und Cursor-Dateien |

Beim Bearbeiten von Ressourcen, wird die Visual Studio-Umgebung funktioniert bei und wirkt sich auf die folgenden Dateien:

| Dateiname | Beschreibung |
|---|---|
| Resource.h | Header-Datei, die von der Entwicklungsumgebung, die enthält Symboldefinitionen generiert.<br/><br/>Diese Datei wird in der quellcodeverwaltung einbeziehen. |
| Filename.aps | Binäre Version von der aktuellen Ressourcenskriptdatei, die zum schnellen Laden verwendet.<br /><br /> Ressourcen-Editoren Lesen nicht direkt. rc- oder resource.h-Dateien. Der Ressourcencompiler kompiliert sie in .aps-Dateien, die von den Ressourcen-Editoren genutzt werden. Diese Datei ist ein Kompilierungsschritt und speichert nur symbolische Daten.<br/><br/>Wie bei einer normalen Kompilierung werden Informationen, die nicht symbolisch z. B. kommentieren, ist während der Kompilierung verworfen.<br/><br/>Sobald die .aps-Datei synchron mit der RC-Datei ist, wird die RC-Datei erneut generiert. Z. B., wenn Sie **speichern**, überschreibt der Ressourcen-Editor, der RC-Datei und resource.h-Datei. Alle Änderungen an den Ressourcen selbst bleiben in der RC-Datei, aber Kommentare gehen immer verloren, sobald die .rc-Datei überschrieben wird. Weitere Informationen zur Erhaltung von Kommentaren, finden Sie unter [sind Ressourcen zur Kompilierungszeit](../windows/how-to-include-resources-at-compile-time.md).<br/><br/>Sie können die .aps-Datei in der Regel sollte nicht in der quellcodeverwaltung einschließen. |
| .rc | Ressourcenskriptdatei, die Skript für die Ressourcen im aktuellen Projekt enthält. Diese Datei wird bei jedem Speichern durch die .aps-Datei überschrieben.<br/><br/>Diese Datei wird in der quellcodeverwaltung einbeziehen. |

## <a name="manifest-resources"></a>Manifestressourcen

In C++-Desktopprojekten werden Ressourcen in einem Dienstmanifest XML-Dateien, die die Abhängigkeiten zu beschreiben, die eine Anwendung verwendet. Definiert z. B. in Visual Studio diese MFC-Assistenten generierte Manifestdatei der Anwendung von der Version des allgemeinen Windows-Steuerelements DLLs verwendet werden soll:

```xml
<description>Your app description here</description>
<dependency>
    <dependentAssembly>
        <assemblyIdentity
            type="win32"
            name="Microsoft.Windows.Common-Controls"
            version="6.0.0.0"
            processorArchitecture="X86"
            publicKeyToken="6595b64144ccf1df"
            language="*"
        />
    </dependentAssembly>
</dependency>
```

Für eine Windows XP oder Windows Vista-Anwendung sollten die Manifestressource die aktuellste Version der allgemeinen Windows-Steuerelemente für die Anwendung zur Verwendung angeben. Das obige Beispiel verwendet die Version `6.0.0.0`, welche unterstützt die [Syslink-Steuerelement](/windows/desktop/Controls/syslink-overview).

> [!NOTE]
> Es kann nur eine Manifestressource pro Modul verwendet werden.

Zum Anzeigen der Version, und geben Sie in einer Manifestressource enthaltenen Informationen, öffnen Sie die Datei in einem XML-Viewer oder den Visual Studio-Text-Editor ein. Beim Öffnen einer Manifestressource aus [Ressourcenansicht](../windows/resource-view-window.md)wird die Ressource im Binärformat geöffnet.

### <a name="to-open-a-manifest-resource"></a>Zum Öffnen einer Manifestressource

1. Öffnen Sie Ihr Projekt in Visual Studio, und navigieren Sie zu **Projektmappen-Explorer**.

1. Erweitern Sie die **Ressourcendateien** Ordner, klicken Sie dann:

   - Um im Text-Editor zu öffnen, doppelklicken Sie auf die *". manifest"* Datei.

   - Um in einem anderen Editor zu öffnen, mit der Maustaste der *". manifest"* und wählen Sie **Öffnen mit**. Geben Sie den Editor, und aktivieren das **öffnen**.

## <a name="requirements"></a>Anforderungen

Win32

## <a name="see-also"></a>Siehe auch

[Arbeiten mit Ressourcendateien](../windows/working-with-resource-files.md)<br/>
[Ressourcenbezeichner (Symbole)](../windows/symbols-resource-identifiers.md)<br/>
[Ressourcen-Editor](../windows/resource-editors.md)<br/>