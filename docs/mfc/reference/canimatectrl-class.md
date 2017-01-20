---
title: "CAnimateCtrl Class"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
f1_keywords: 
  - "CAnimateCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "animation controls [C++], CAnimateCtrl class"
  - "CAnimateCtrl class"
  - "Windows common controls [C++], CAnimateCtrl class"
ms.assetid: 5e8eb1bd-96b7-47b8-8de2-6bcbb3cc299b
caps.latest.revision: 25
caps.handback.revision: "13"
ms.author: "mblome"
manager: "ghogen"
---
# CAnimateCtrl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Stellt die Funktionalität des allgemeinen Animationssteuerelements Windows bereit.  
  
## Syntax  
  
```  
  
class CAnimateCtrl : public CWnd  
  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CAnimateCtrl::CAnimateCtrl](../Topic/CAnimateCtrl::CAnimateCtrl.md)|Erstellt ein `CAnimateCtrl`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CAnimateCtrl::Close](../Topic/CAnimateCtrl::Close.md)|Enthält den AVI\-Klipp.|  
|[CAnimateCtrl::Create](../Topic/CAnimateCtrl::Create.md)|Erstellt ein Animationssteuerung und fügt es zu einem `CAnimateCtrl`\-Objekt.|  
|[CAnimateCtrl::CreateEx](../Topic/CAnimateCtrl::CreateEx.md)|Erstellt ein Animationssteuerung mit den angegebenen Windows\-erweitertenFormaten und fügt es zu einem `CAnimateCtrl`\-Objekt.|  
|[CAnimateCtrl::IsPlaying](../Topic/CAnimateCtrl::IsPlaying.md)|Gibt an, ob ein Klipp Audio Video Interleaveds \(AVI\) wiedergibt.|  
|[CAnimateCtrl::Open](../Topic/CAnimateCtrl::Open.md)|Öffnet einen AVI\-Klipp aus einer Datei oder einer Ressource und zeigt die ersten Frames angezeigt.|  
|[CAnimateCtrl::Play](../Topic/CAnimateCtrl::Play.md)|Gibt den AVI\-Klipp ohne Sound wieder.|  
|[CAnimateCtrl::Seek](../Topic/CAnimateCtrl::Seek.md)|Zeigt ausgewählten einzelner Rahmen des AVI\-Klipps an.|  
|[CAnimateCtrl::Stop](../Topic/CAnimateCtrl::Stop.md)|Überwacht auf, den AVI\-Klipp wiederzugeben.|  
  
## Hinweise  
 Dieses Steuerelement \(und daher die `CAnimateCtrl`\-Klasse\) ist nur für \- Programmen verfügbar, die unter Windows 95, Windows 98 und Windows NT 3,51 und höher ausgeführt werden.  
  
 Ein Animationssteuerung ist ein rechteckiges Fenster, das einen Klipp im Format AVI \(Audio Video Interleaved\) das Standard\-Windows\-Video\/das Audioformat anzeigt.  Ein AVI\-Klipp ist eine Reihe von Bitmapframes, wie ein Film.  
  
 Animationssteuerelemente können nur einfache AVI\-Klipps wiedergeben.  Insbesondere müssen die durch ein Animationssteuerung wiedergegeben werden Klipps, die folgenden Anforderungen erfüllen:  
  
-   Es muss einen Videostream genau geben und er muss eine Frames verfügen.  
  
-   Es kann zwei Streams in der Datei höchstens geben \(in der Regel ist der andere Stream, wenn sich darstellen, ein Audiostream, obwohl das Animationssteuerung Audioinformationen ignoriert\).  
  
-   Der Klipp muss entweder mit Komprimierung RLE8 dekomprimiert oder komprimiert sein.  
  
-   Keine Palettenänderungen werden im Videostream zulässig.  
  
 Sie können den AVI\-Klipp der Anwendung als AVI\-Ressource hinzufügen, oder sie kann die Anwendung als separate AVI\-Datei steht.  
  
 Da der Thread die Ausführung fortsetzt, während der AVI\-Klipp angezeigt wird, ist eine übliche Verwendung für ein Animationssteuerung, Systemaktivität während eines längeren Vorgangs anzugeben.  Beispielsweise werden durch Suchendialogfeld des Datei\-Explorers verschiebbar Lupe als die Systemsuchen für eine Datei an.  
  
 Wenn Sie ein `CAnimateCtrl`\-Objekt innerhalb eines Dialogfelds oder einer Dialogfeldressource mithilfe des Dialog\-Editors erstellen, wird dieser automatisch zerstört, wenn der Benutzer das Dialogfeld geschlossen wird.  
  
 Wenn Sie ein `CAnimateCtrl`\-Objekt innerhalb eines Fensters erstellen, müssen Sie es zerstören.  Wenn Sie das `CAnimateCtrl`\-Objekt auf dem Stapel erstellen, wird er automatisch zerstört.  Wenn Sie das `CAnimateCtrl`\-Objekt auf dem Heap erstellen, indem Sie die **new**\-Funktion verwenden, müssen Sie **delete** für das Objekt aufrufen, um es zu zerstören.  Wenn Sie eine neue Klasse von ableiten und `CAnimateCtrl` jeden Speicher in dieser Klasse zuordnen, überschreiben Sie den `CAnimateCtrl` Destruktor, um die Zuordnungen freizugeben.  
  
 Weitere Informationen zur Verwendung von `CAnimateCtrl`, finden Sie unter [Steuerelemente](../../mfc/controls-mfc.md) und [Verwenden CAnimateCtrl](../../mfc/using-canimatectrl.md).  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CAnimateCtrl`  
  
## Anforderungen  
 **Header:**  afxcmn.h  
  
## Siehe auch  
 [CWnd\-Klasse](../../mfc/reference/cwnd-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CAnimateCtrl::Create](../Topic/CAnimateCtrl::Create.md)   
 [ON\_CONTROL](../Topic/ON_CONTROL.md)