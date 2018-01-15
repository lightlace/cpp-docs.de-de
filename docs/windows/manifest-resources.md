---
title: Manifestressourcen | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- manifest resources
- resources [Visual Studio], manifest
ms.assetid: 8615334c-22a0-44c0-93e0-5924528c9917
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 56a41a7901e41f4c76fbb9fcbf5930ec97c3b866
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="manifest-resources"></a>Manifestressourcen
Manifestressourcen sind XML-Dateien zur Beschreibung der von einer Anwendung verwendeten Abhängigkeiten. In Visual Studio wird durch die vom MFC-Assistenten generierte Manifestdatei z. B. definiert, welche DLLs allgemeiner Windows-Steuerelemente, Version 5.0 oder 6.0, von der Anwendung verwendet werden sollen:  
  
```  
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
  
 Um die in einer Manifestressource enthaltenen Versions- und Typinformationen anzuzeigen, können Sie die Datei in einem XML-Viewer oder im [Text-Editor](http://msdn.microsoft.com/en-us/508e1f18-99d5-48ad-b5ad-d011b21c6ab1)von Visual Studio öffnen. Weitere Informationen finden Sie unter [Öffnen einer Manifestressource im Text-Editor von Visual Studio](../windows/how-to-open-a-manifest-resource.md).  
  
 Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *.NET Framework-Entwicklerhandbuch.* Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, zum Zugreifen auf Ressourcen, zum Anzeigen statischer Ressourcen und zum Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften finden Sie unter  [Walkthrough: Using Resources for Localization with ASP.NET](http://msdn.microsoft.com/Library/bb4e5b44-e2b0-48ab-bbe9-609fb33900b6)unterstützt.  
  
## <a name="limitations"></a>Einschränkungen  
 Es kann nur eine Manifestressource pro Modul verwendet werden.  
  
## <a name="requirements"></a>Anforderungen  
 Win32  
  
## <a name="see-also"></a>Siehe auch  
 [Steuerelemente](../mfc/controls-mfc.md)   
 [Arbeiten mit Ressourcendateien](../windows/working-with-resource-files.md)