---
title: Manifestressourcen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- manifest resources
- resources [Visual Studio], manifest
ms.assetid: 8615334c-22a0-44c0-93e0-5924528c9917
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 1c9a1786e5b3a6fb150e3e27fb459ac4341486ca
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42604787"
---
# <a name="manifest-resources"></a>Manifestressourcen

Manifestressourcen sind XML-Dateien zur Beschreibung der von einer Anwendung verwendeten Abhängigkeiten. In Visual Studio wird durch die vom MFC-Assistenten generierte Manifestdatei z. B. definiert, welche DLLs allgemeiner Windows-Steuerelemente, Version 5.0 oder 6.0, von der Anwendung verwendet werden sollen:

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

Bei Windows XP- oder Windows Vista-Anwendungen gibt die Manifestressource nicht nur an, dass die Anwendung die aktuellste Version der allgemeinen Windows-Steuerelemente (v6.0, wie oben dargestellt) verwendet, sondern dass sie darüber hinaus das [Syslink-Steuerelement](http://msdn.microsoft.com/library/windows/desktop/bb760706)unterstützt.

Zum Anzeigen der Version, und geben Sie in einer Manifestressource enthaltenen Informationen, können Sie die Datei öffnen, in einem XML-Viewer oder im Visual Studio [Text-Editor](http://msdn.microsoft.com/508e1f18-99d5-48ad-b5ad-d011b21c6ab1). Weitere Informationen finden Sie unter [Öffnen einer Manifestressource im Text-Editor von Visual Studio](../windows/how-to-open-a-manifest-resource.md).

Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *(.NET Framework Developer's Guide*. Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, zum Zugreifen auf Ressourcen, zum Anzeigen statischer Ressourcen und zum Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften finden Sie unter  [Walkthrough: Using Resources for Localization with ASP.NET](http://msdn.microsoft.com/Library/bb4e5b44-e2b0-48ab-bbe9-609fb33900b6)unterstützt.

## <a name="limitations"></a>Einschränkungen

Es kann nur eine Manifestressource pro Modul verwendet werden.

## <a name="requirements"></a>Anforderungen

Win32

## <a name="see-also"></a>Siehe auch

[Steuerelemente](../mfc/controls-mfc.md)  
[Arbeiten mit Ressourcendateien](../windows/working-with-resource-files.md)