---
title: Manifestressourcen Sie (C++)
ms.date: 11/04/2016
helpviewer_keywords:
- manifest resources [C++]
- resources [C++], manifest
ms.assetid: 8615334c-22a0-44c0-93e0-5924528c9917
ms.openlocfilehash: 081fd12a86c31973c7856ca7b9f3fcb129e2eb81
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50578281"
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

Zum Anzeigen der Version, und geben Sie in einer Manifestressource enthaltenen Informationen, können Sie die Datei in einem XML-Viewer oder im Visual Studio-Text-Editor öffnen. Weitere Informationen finden Sie unter [Öffnen einer Manifestressource im Text-Editor von Visual Studio](../windows/how-to-open-a-manifest-resource.md).

Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *(.NET Framework Developer's Guide*.

## <a name="limitations"></a>Einschränkungen

Es kann nur eine Manifestressource pro Modul verwendet werden.

## <a name="requirements"></a>Anforderungen

Win32

## <a name="see-also"></a>Siehe auch

[Steuerelemente](../mfc/controls-mfc.md)<br/>
[Arbeiten mit Ressourcendateien](../windows/working-with-resource-files.md)