---
title: "Accessing Version Information from Within Your Program | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.editors.version"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "VerQueryValue"
  - "version information, accessing from within programs"
  - "GetFileVersionInfo"
  - "version information"
ms.assetid: 18622333-d9e8-4309-9465-677cd10c79b1
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Accessing Version Information from Within Your Program
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

### So greifen Sie aus Ihrem Programm auf Versionsinformationen zu  
  
1.  Wenn Sie aus ihrem Programm auf die Versionsinformationen zugreifen möchten, verwenden Sie die Funktion [GetFileVersionInfo](http://msdn.microsoft.com/library/windows/desktop/ms647003.aspx) und die Funktion [VerQueryValue](http://msdn.microsoft.com/library/windows/desktop/ms647464.aspx).  
  
 Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Anwendungen](../Topic/Resources%20in%20Desktop%20Apps.md) im *.NET Framework\-Entwicklerhandbuch.* Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, zum Zugreifen auf Ressourcen, zum Anzeigen statischer Ressourcen und zum Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften finden Sie unter [Exemplarische Vorgehensweise: Lokalisieren von Windows Forms](assetId:///9a96220d-a19b-4de0-9f48-01e5d82679e5) und [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
 **Anforderungen**  
  
 Win32  
  
## Siehe auch  
 [Version Information Editor](../mfc/version-information-editor.md)   
 [Versionsinformationen \(Windows\)](https://msdn.microsoft.com/library/windows/desktop/ms646981.aspx)