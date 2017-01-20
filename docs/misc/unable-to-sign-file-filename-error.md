---
title: "Die Datei &#39;&lt;Dateiname&gt;&#39; kann nicht signiert werden: &lt;Fehler&gt;"
ms.custom: na
ms.date: "10/29/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "bc31028"
  - "vbc31028"
helpviewer_keywords: 
  - "BC31028"
ms.assetid: 2cb22e75-5ee2-4e07-afc0-680a0bd543d4
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "shoag"
manager: "wpickett"
---
# Die Datei &#39;&lt;Dateiname&gt;&#39; kann nicht signiert werden: &lt;Fehler&gt;
Beim Signieren der angegebenen Datei ist ein Fehler aufgetreten. Dieser Fehler kann verschiedene Ursachen haben:  
  
-   Unzureichende Berechtigungen.  
  
-   Fehlende Systemdateien, die für die Authenticode\-Signatur erforderlich sind.  
  
-   Ein Verweis auf ein nicht vorhandenes Zertifikat oder die nicht vorhandene Datei des privaten Schlüssels.  
  
-   Falsche Schreibweise für einen Dateinamen oder eine URL.  
  
 **Fehler\-ID:** BC31028  
  
### So beheben Sie diesen Fehler  
  
1.  Geben Sie den richtigen Namen für das Zertifikat und die Datei des privaten Schlüssels ein.  
  
2.  Wenn Sie die Authenticode\-Signatur verwenden, überprüfen Sie, ob die Dateien „Signcode.exe“ und „Javasign.dll“ vorhanden sind und deren Schreibschutzattribut nicht festgelegt ist.  
  
3.  Stellen Sie sicher, dass Sie über die Berechtigung `Write` für die Datei verfügen.  
  
## Siehe auch  
 [File Signing Tool \(Signcode.exe\)](assetId:///2d299154-34ea-41ba-ad12-17075bb7e1db)   
 [Deployment and Authenticode Signing](assetId:///ecc3f059-da2e-445b-9b87-5b2978e2f8b2)