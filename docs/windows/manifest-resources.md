---
title: Manifestressourcen Sie (C++)
ms.date: 11/04/2016
helpviewer_keywords:
- manifest resources [C++]
- resources [C++], manifest
- resources [C++], opening
ms.assetid: 8615334c-22a0-44c0-93e0-5924528c9917
ms.openlocfilehash: 2d135cb2d512313f107eef7e95ec90d7972b68b4
ms.sourcegitcommit: bd637e9c39650cfd530520ea978a22fa4caa0e42
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/07/2019
ms.locfileid: "55850189"
---
# <a name="manifest-resources-c"></a>Manifestressourcen Sie (C++)

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

Bei Windows XP- oder Windows Vista-Anwendungen gibt die Manifestressource nicht nur an, dass die Anwendung die aktuellste Version der allgemeinen Windows-Steuerelemente (v6.0, wie oben dargestellt) verwendet, sondern dass sie darüber hinaus das [Syslink-Steuerelement](/windows/desktop/Controls/syslink-overview)unterstützt.

Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *(.NET Framework Developer's Guide*.

Zum Anzeigen der Version, und geben Sie in einer Manifestressource enthaltenen Informationen, können Sie die Datei in einem XML-Viewer oder im Visual Studio-Text-Editor öffnen. Beim Öffnen einer Manifestressource aus [Ressourcenansicht](../windows/resource-view-window.md)wird die Ressource im Binärformat geöffnet. Um den Inhalt einer Manifestressource in einem besser lesbaren Format anzuzeigen, müssen Sie die Ressource aus öffnen **Projektmappen-Explorer**.

## <a name="to-open-a-manifest-resource-in-the-text-editor"></a>Öffnen einer Manifestressource im Text-Editor

1. Mit das Projekt im **Projektmappen-Explorer**, erweitern Sie die **Ressourcendateien** Ordner.

1. Doppelklicken Sie auf die .manifest-Datei.

   Die Manifestressource wird geöffnet, der **Text-Editor**.

## <a name="to-open-a-manifest-resource-in-another-editor"></a>Öffnen einer Manifestressource in einem anderen Editor

1. In **Projektmappen-Explorer**mit der rechten Maustaste auf die .manifest-Datei, und wählen Sie **Öffnen mit...**  aus dem Kontextmenü.

1. In der **Öffnen mit** Dialogfeld Geben Sie den Editor, Sie möchten, und aktivieren Sie **öffnen**.

## <a name="limitations"></a>Einschränkungen

Es kann nur eine Manifestressource pro Modul verwendet werden.

## <a name="requirements"></a>Anforderungen

Win32

## <a name="see-also"></a>Siehe auch

[Steuerelemente](../mfc/controls-mfc.md)<br/>
[Arbeiten mit Ressourcendateien](../windows/working-with-resource-files.md)