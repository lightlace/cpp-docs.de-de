---
title: Manifestressourcen (C++) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- manifest resources [C++]
- resources [C++], manifest
ms.assetid: 8615334c-22a0-44c0-93e0-5924528c9917
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 6d58e89250708f264ff6bb96c75e8124ffa02509
ms.sourcegitcommit: f0c90000125a9497bf61e41624de189a043703c0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2018
ms.locfileid: "44316444"
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

Für eine Windows XP oder Windows Vista-Anwendung gibt die Manifestressource nicht nur, dass die Anwendung die aktuellste Version der allgemeinen Windows-Steuerelemente (v6. 0, wie oben gezeigt), sondern zudem unterstützt die [Syslink-Steuerelement](/windows/desktop/Controls/syslink-overview).

Zum Anzeigen der Version, und geben Sie in einer Manifestressource enthaltenen Informationen, können Sie die Datei in einem XML-Viewer oder im Visual Studio-Text-Editor öffnen. Weitere Informationen finden Sie unter [Öffnen einer Manifestressource im Text-Editor von Visual Studio](../windows/how-to-open-a-manifest-resource.md).

Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *(.NET Framework Developer's Guide*.

## <a name="limitations"></a>Einschränkungen

Es kann nur eine Manifestressource pro Modul verwendet werden.

## <a name="requirements"></a>Anforderungen

Win32

## <a name="see-also"></a>Siehe auch

[Steuerelemente](../mfc/controls-mfc.md)  
[Arbeiten mit Ressourcendateien](../windows/working-with-resource-files.md)