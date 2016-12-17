---
title: "Verwenden einer Dialogleiste mit einem Grundleisten-Steuerelement"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "WM_EX_TRANSPARENT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Dialogleisten, Verwenden mit Rebarbereichen"
  - "rebar-Steuerelemente, Dialogleisten"
  - "WS_EX_TRANSPARENT-Stile"
ms.assetid: e528cea0-6b81-4bdf-9643-7c03b6176590
caps.latest.revision: 11
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Verwenden einer Dialogleiste mit einem Grundleisten-Steuerelement
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wie in der [Infoleistensteuerelemente und Bänder](../mfc/rebar-controls-and-bands.md) erwähnt, kann jedes Band nur ein untergeordnetes Fenster \(oder Steuerelement\) enthalten.  Dies kann eine Einschränkung, wenn mehr als ein untergeordnetes Fenster pro Band haben möchten.  Eine einfache Problemumgehung ist, eine Dialogleistenressource mit mehreren Steuerelementen und einem Infoleistenband \(die Dialogleiste enthalten\) dem Grundleistensteuerelement hinzuzufügen.  
  
 Normalerweise wenn Sie das Dialogleistenband transparent dargestellt werden können, würden Sie das **WS\_EX\_TRANSPARENT** erweiterte Format für das Dialogleistenobjekt festlegen.  Da **WS\_EX\_TRANSPARENT** verschiedener Probleme mit den Hintergrund einer Dialogleiste ordnungsgemäß zeichnen ist, müssen Sie zusätzliche Arbeit etwas ausführen, um den gewünschten Effekt zu erreichen.  
  
 In der folgenden Prozedur werden ausführlich die Schritte aufgeführt, die erforderlich sind, Transparenz zu erreichen, das ohne **WS\_EX\_TRANSPARENT** erweiterte Format zu verwenden.  
  
### Um eine transparente Dialogleiste in einer Infoleiste implementieren bieten ein Band  
  
1.  Mit [Fügen Sie Klassendialogfeld hinzu](../mfc/reference/adding-an-mfc-class.md) fügen Sie eine neue Klasse \(beispielsweise `CMyDlgBar`\), diese Implementierung das Dialogleistenobjekt hinzu.  
  
2.  Fügen Sie Handler für die `WM_ERASEBKGND` \- Meldung hinzugefügt.  
  
3.  Im neuen Handler ändern Sie den vorhandenen Code, um das folgende Beispiel:  
  
     [!CODE [NVC_MFCControlLadenDialog#29](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCControlLadenDialog#29)]  
  
4.  Fügen Sie Handler für die `WM_MOVE` \- Meldung hinzugefügt.  
  
5.  Im neuen Handler ändern Sie den vorhandenen Code, um das folgende Beispiel:  
  
     [!CODE [NVC_MFCControlLadenDialog#30](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCControlLadenDialog#30)]  
  
 Die neuen Handler simulieren die Transparenz der Dialogleiste, indem sie die `WM_ERASEBKGND` Meldung am übergeordneten Fenster weiterleiten und ein Neu Das erzwingen, wenn das Dialogleistenobjekt verschoben wird.  
  
## Siehe auch  
 [Verwenden von CReBarCtrl](../mfc/using-crebarctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)