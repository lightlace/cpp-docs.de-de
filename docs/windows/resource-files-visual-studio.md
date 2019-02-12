---
title: Ressourcendateien (C++)
ms.date: 11/04/2016
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
ms.openlocfilehash: 65500644b70841f372edcc6911edefc6c7b9f432
ms.sourcegitcommit: f4be868c0d1d78e550fba105d4d3c993743a1f4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/12/2019
ms.locfileid: "56152689"
---
# <a name="resource-files-c"></a>Ressourcendateien (C++)

> [!NOTE]
> Diese Materialien beziehen sich auf Windows-Desktopanwendungen. Weitere Informationen zu Ressourcen in die universelle Windows-Plattform-apps finden Sie unter [Definieren von App-Ressourcen](/windows/uwp/app-resources/).
>
> Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *(.NET Framework Developer's Guide*. Weitere Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, den Zugriff auf Ressourcen, zum Anzeigen statischer Ressourcen und Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften, finden Sie unter [Erstellen von Ressourcendateien für Desktop-Apps](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Weitere Informationen zur Globalisierung und Lokalisierung von Ressourcen in verwalteten apps finden Sie unter [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).
>
> Da Projekte in .NET-Programmiersprachen keine Ressourcenskriptdateien verwenden, müssen Sie Ihre Ressourcen im **Projektmappen-Explorer**. Mit der [Bildbearbeitung](../windows/image-editor-for-icons.md) und dem [Binär-Editor](binary-editor.md) ist die Bearbeitung von Ressourcendateien in verwalteten Projekten möglich. Bei den zu bearbeitenden verwalteten Ressourcen muss es sich um verknüpfte Ressourcen handeln. Das Bearbeiten eingebetteter Ressourcen wird von den Visual Studio-Ressourcen-Editoren nicht unterstützt.

Der Begriff „Ressourcendatei“ kann sich auf verschiedene Dateitypen beziehen, einschließlich dieser:

- Die Ressourcenskriptdatei (RC) eines Programms.

- Eine Ressourcenvorlagendatei (RCT).

- Eine einzelne Ressource, die als eigenständige Datei vorliegt, wie etwa eine Bitmap-, eine Symbol- oder eine Cursordatei, auf die von einer RC-Datei verwiesen wird.

- Eine von der Entwicklungsumgebung generierte Headerdatei, beispielsweise „Resource.h“, auf die von einer RC-Datei verwiesen wird.

Ressourcen befinden sich auch unter [andere Dateitypen](../windows/editable-file-types-for-resources.md) z. B. .exe, DLL und RES-Dateien. Sie können mit Ressourcen und Ressourcendateien aus arbeiten, in Ihrem Projekt und diejenigen, die nicht Teil des aktuellen Projekts sind. Sie können auch mit Ressourcendateien arbeiten, die in der Entwicklungsumgebung von Visual Studio nicht erstellt worden wäre. Sie haben unter anderem folgende Möglichkeiten:

- Arbeiten mit geschachtelten und bedingt eingeschlossenen Ressourcendateien.

- Aktualisieren vorhandener Ressourcen oder Konvertierung vorhandener Ressourcen in das Visual C++-Format.

- Importieren oder Exportieren grafischer Ressourcendateien in die oder aus der aktuelle(n) Ressourcendatei.

- Einschließen gemeinsam verwendeter oder schreibgeschützter Bezeichner (Symbole), die von der Entwicklungsumgebung nicht geändert werden können.

- Schließen Sie Ressourcen in Ihre ausführbaren Dateien (.exe)-Datei keine Bearbeitung erfordern (oder, sollte nicht bearbeitet werden kann), Rahmen des aktuellen Projekts, z. B. freigegebene Ressourcen von mehreren Projekten ein.

- Einschließen von Ressourcentypen, die von der Entwicklungsumgebung nicht unterstützt werden.

Die folgenden Typen von Dateien zu öffnen können und bearbeiten die darin enthaltenen Ressourcen:

|Dateiname|Beschreibung|
|---------------|-----------------|
|.rc|Ressourcenskriptdateien|
|.rct|Ressourcenvorlagendateien|
|.res|Ressourcendateien|
|.resx|Verwaltete Ressourcendateien|
|.exe|Ausführbare Dateien.|
|.dll|Dynamic Link Library-Dateien.|
|.bmp, .ico, .dib und .cur|Bitmap-, Symbol-, Symbolleisten- und Cursordateien|

Visual Studio-Umgebung funktioniert bei und wirkt sich auf die Dateien, die in der folgenden Tabelle gezeigt wird, während Ihrer Sitzung zur Bearbeitung von Ressourcen:

|Dateiname|Beschreibung|
|---------------|-----------------|
|Resource.h|Durch die Entwicklungsumgebung generierte Headerdatei; enthält Symboldefinitionen. (Enthalten Sie diese Datei in der quellcodeverwaltung.)|
|Filename.aps|Binäre Version der aktuellen Ressourcenskriptdatei; zum schnellen Laden verwendet.<br /><br /> Die Ressourcen-Editoren Lesen nicht direkt. rc- oder resource.h-Dateien. Der Ressourcencompiler kompiliert sie in .aps-Dateien, die von den Ressourcen-Editoren genutzt werden. Diese Datei ist ein Kompilierungsschritt und speichert nur symbolische Daten. Wie bei einer normalen Kompilierung werden Informationen, die nicht symbolisch sind (z. B. Kommentare) ist während der Kompilierung verworfen. Sobald die .aps-Datei nicht mehr mit der .rc-Datei synchron ist, wird die .rc-Datei neu generiert (z. B. überschreibt der Ressourcen-Editor beim Speichern die .rc-Datei und resource.h-Datei). Alle Änderungen an den Ressourcen selbst bleiben in der .rc-Datei, aber Kommentare gehen immer verloren, sobald die .rc-Datei überschrieben wird. Weitere Informationen zur Erhaltung von Kommentaren, finden Sie unter [Einfügen von Ressourcen zur Kompilierungszeit](../windows/how-to-include-resources-at-compile-time.md). (In der Regel sollte nicht Sie die .aps-Datei in der quellcodeverwaltung enthalten.)|
|.rc|Ressourcenskriptdatei, die Skript für die Ressourcen im aktuellen Projekt enthält. Diese Datei wird bei jedem Speichern durch die .aps-Datei überschrieben. (Enthalten Sie diese Datei in der quellcodeverwaltung.)|

Dieser Abschnitt enthält Gewusst wie:

- [Erstellen von Ressourcen](../windows/how-to-create-a-resource-script-file.md)

- [Verwalten von Ressourcen](../windows/how-to-copy-resources.md)

- [Einfügen von Ressourcen zur Kompilierungszeit](../windows/how-to-include-resources-at-compile-time.md)

## <a name="manifest-resources"></a>Manifestressourcen

In C++-Desktopprojekten werden Ressourcen in einem Dienstmanifest XML-Dateien, die die Abhängigkeiten zu beschreiben, die eine Anwendung verwendet. In Visual Studio wird durch die vom MFC-Assistenten generierte Manifestdatei z. B. definiert, welche DLLs allgemeiner Windows-Steuerelemente, Version 5.0 oder 6.0, von der Anwendung verwendet werden sollen:

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

Für eine Windows XP oder Windows Vista-Anwendung gibt die Manifestressource nicht nur, dass die Anwendung die aktuellste Version der allgemeinen Windows-Steuerelemente, V6. 0 verwenden, wie oben zu sehen, aber sie auch unterstützt die [Syslink-Steuerelement](/windows/desktop/Controls/syslink-overview).

Zum Anzeigen der Version, und geben Sie in einer Manifestressource enthaltenen Informationen, können Sie die Datei in einem XML-Viewer oder im Visual Studio-Text-Editor öffnen. Beim Öffnen einer Manifestressource aus [Ressourcenansicht](../windows/resource-view-window.md)wird die Ressource im Binärformat geöffnet. Um den Inhalt einer Manifestressource in einem besser lesbaren Format anzuzeigen, müssen Sie die Ressource aus öffnen **Projektmappen-Explorer**.

Wählen Sie zum Öffnen einer Manifestressource aus die folgenden Schritte aus:

- Für Text-Editor, während Ihr Projekt in **Projektmappen-Explorer**, erweitern Sie die **Ressourcendateien** Ordner und doppelklicken Sie auf die .manifest-Datei.

- Für einen anderen Editor in **Projektmappen-Explorer**mit der rechten Maustaste auf die .manifest-Datei, und wählen Sie **Öffnen mit...**  aus dem Kontextmenü. In der **Öffnen mit** Dialogfeld Geben Sie den Editor, Sie möchten, und aktivieren Sie **öffnen**.

> [!NOTE]
> Es kann nur eine Manifestressource pro Modul verwendet werden.

## <a name="requirements"></a>Anforderungen

Win32

## <a name="see-also"></a>Siehe auch

[Ressourcen-Editor](../windows/resource-editors.md)<br/>
[Arbeiten mit Ressourcendateien](../windows/working-with-resource-files.md)<br/>
[Menüs und weitere Ressourcen](https://msdn.microsoft.com/library/windows/desktop/ms632583.aspx)<br/>
[Steuerelemente](../mfc/controls-mfc.md)<br/>