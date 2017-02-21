---
title: "Einschr&#228;nkungen f&#252;r CImage in fr&#252;heren Betriebssystemen | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CImage"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CImage-Klasse, Einschränkungen"
ms.assetid: 4bedaab8-7dd1-4c91-ab35-b75fb56765b0
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Einschr&#228;nkungen f&#252;r CImage in fr&#252;heren Betriebssystemen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Viele `CImage`\-Funktionen funktionieren nur mit neueren Windows\-Versionen: Windows 95\/98 oder Windows NT 4.0 oder Windows 2000.  In diesem Artikel werden die Versionseinschränkungen bestimmter Methoden.  
  
 [CImage::PlgBlt](../Topic/CImage::PlgBlt.md) und [CImage::MaskBlt](../Topic/CImage::MaskBlt.md) arbeiten mit nur Windows NT 4.0 oder höher.  Sie arbeiten nicht an Anwendungen unter auf Windows 95\/98 oder höher.  
  
 [CImage::AlphaBlend](../Topic/CImage::AlphaBlend.md) und [CImage::TransparentBlt](../Topic/CImage::TransparentBlt.md) arbeiten mit nur Windows 2000 oder höher und Windows 98 oder höher, da Sie mit msimg32.lib verknüpfen müssen, um diese Methoden zu verwenden. \(Diese Bibliothek ist nur für Anwendungen verfügbar, die Windows 2000 oder höher und Windows 98 oder höher. ausführen\)  
  
 Sie können `AlphaBlend` und `TransparentBlt` in einer Anwendung beinhalten, die auf Windows 95 oder Windows NT 4.0 ausgeführt wird, wenn diese Methoden nicht aufgerufen werden.  Wenn die Anwendung diese Methoden enthält und sie auf frühere Betriebssysteme ausgeführt werden muss, müssen Sie [\/delayload](../build/reference/delayload-delay-load-import.md) des Linkers verwenden, um das Laden von msimg32.lib hinauszuzögern.  Solange die Anwendung keine dieser Methoden bei Ausführung unter Windows NT 4.0 oder Windows 95 aufruft, versucht sie nicht, msimg32.lib zu laden.  Sie können überprüfen, ob Transparenzunterstützung verfügbar ist, die `CImage::IsTransparencySupported`\-Methode anwendend.  
  
## Beispiel  
 [!CODE [NVC_MFCDocViewSDI#8](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCDocViewSDI#8)]  
  
 Zum Kompilieren einer Anwendung die diese Methoden aufruft, fügen Sie eine \#define \_WIN32\_WINNT Anweisung ein bevor Sie eine \#including Systemheadern dupliziert wird und angeben dass die Version von Windows gleich oder größer als 5.0 ist:  
  
 [!CODE [NVC_MFCDocViewSDI#9](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCDocViewSDI#9)]  
  
 Wenn die Anwendung nicht erforderlich, um auf ein Betriebssystemälteres als Windows 2000 oder Windows 98 ausgeführt werden, können Sie direkt zu msimg32.lib verknüpfen, ohne eine **\/delayload** zu verwenden.  
  
 [CImage::Draw](../Topic/CImage::Draw.md) verhält sich anders, wenn es bei Windows 2000 und Windows 98 verwendet wird, als das mit Windows NT 4.0 oder Windows 95.  
  
 Wenn Sie die Anwendung mit \_WIN32\_WINNT kompilieren, das auf einen Wert kleiner als 0x0500 festgelegt ist, verwendet **Zeichnen**, jedoch behandelt Transparenz nicht automatisch auf Systemen, die Windows 2000 und Windows 98 und höher ausgeführt.  
  
 Wenn Sie die Anwendung mit 0x0500 festgelegtem oder größerem \_WIN32\_WINNT kompilieren, behandelt **Zeichnen** Transparenz automatisch auf Systemen, die Windows 2000 oder Windows 98 und höher ausgeführt.  Er funktioniert auch, aber ohne Transparenzunterstützung, mit Windows NT 4.0 und Windows 95; jedoch müssen Sie **\/delayload** verwenden, um das Laden von msimg32.LIB zu verzögern, wie für `AlphaBlend` und `TransparentBlt` oben beschrieben.  
  
## Siehe auch  
 [CImage Class](../atl-mfc-shared/reference/cimage-class.md)