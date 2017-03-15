---
title: "Bereitstellen von Mausinteraktionen in inaktiven Steuerelementen | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MFC-ActiveX-Steuerelemente, Mausinteraktion"
ms.assetid: b09106bf-44c7-4b9b-a6d9-0d624f16f5b3
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Bereitstellen von Mausinteraktionen in inaktiven Steuerelementen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wenn das Steuerelement nicht sofort aktiviert ist, sollten Sie jedoch `WM_SETCURSOR` und `WM_MOUSEMOVE` aufrufen, obwohl das Steuerelement kein Fenster von eigenen hat.  Dies kann erreicht werden, indem `COleControl` Implementierung der Schnittstelle `IPointerInactive` aktiviert, die standardmäßig deaktiviert ist. \(Siehe das *ActiveX\-SDK*  für eine Beschreibung dieser Schnittstelle.\) Um sie zu aktivieren, fügen Sie das `pointerInactive`\-Flag im Satz von Flags ein, die von [COleControl::GetControlFlags](../Topic/COleControl::GetControlFlags.md) zurückgegeben werden:  
  
 [!CODE [NVC_MFC_AxOpt#5](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_AxOpt#5)]  
[!CODE [NVC_MFC_AxOpt#10](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_AxOpt#10)]  
[!CODE [NVC_MFC_AxOpt#7](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_AxOpt#7)]  
  
 Der Code, mit dem dieses Flags einzuschließen wird automatisch generiert, wenn Sie die Option **Mauszeiger\-Benachrichtigung wenn inaktiv** auf der Seite [Steuerelementeinstellungen](../mfc/reference/control-settings-mfc-activex-control-wizard.md) auswählen, wenn Sie das Steuerelement mit **MFC\-ActiveX\-Steuerelement\-Assistent** erstellen.  
  
 Wenn die `IPointerInactive`\-Schnittstelle aktiviert wird, delegiert der Container `WM_SETCURSOR` und `WM_MOUSEMOVE` Meldungen dorthin.  `COleControl` Implementierung von `IPointerInactive` leitet die Meldungen durch die Meldungszuordnung des Steuerelements weiter, nachdem die Mauskoordinaten entsprechend anpassen.  Sie können die Meldungen wie gewöhnliche Fenstermeldungen verarbeiten, indem Sie den entsprechenden Einträgen zur Meldungszuordnung hinzufügen.  In den Handler für diese Meldungen, vermeiden Sie es, die `m_hWnd`\-Membervariable \(oder eine Memberfunktion, die sie verwendet\), ohne zuerst die Prüfung zu verwenden, dass der Wert nicht **NULL** ist.  
  
 Sie können auch ein Präprozessordirektiven Steuerelement das Ziel eines Drag & Drop\-Vorgangs sein.  Dies erfordert das Aktivieren des Steuerelements, in dem von Ihnen angegebenen Zeitpunkt als der Benutzer ein Objekt darüber zieht, sodass das Fenster des Steuerelements als Ablageziel registriert werden kann.  Um Aktivierung zu bewirken während eines Ziehvorgangs fungiert, überschreiben Sie [COleControl::GetActivationPolicy](../Topic/COleControl::GetActivationPolicy.md) und geben Sie das Flag **POINTERINACTIVE\_ACTIVATEONDRAG** zurück:  
  
 [!CODE [NVC_MFC_AxOpt#11](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_AxOpt#11)]  
  
 Die `IPointerInactive`\-Schnittstelle zu aktivieren bedeutet normalerweise, dass Sie das Steuerelement an Mausmeldungen jederzeit verarbeiten Lage sein soll.  Um dieses Verhalten in einem Container abzurufen der nicht die `IPointerInactive`\-Schnittstelle unterstützt, müssen Sie das Steuerelement, das immer falls sichtbar aktiviert ist, das heißt dass das Steuerelement das Flag **OLEMISC\_ACTIVATEWHENVISIBLE** unter den verschiedenen Flags enthalten soll.  Um zu verhindern dass dieses Flag in einem Container, der `IPointerInactive` unterstützt, können Sie das **OLEMISC\_IGNOREACTIVATEWHENVISIBLE**\-Flag auch angeben wirksam wird:  
  
 [!CODE [NVC_MFC_AxOpt#12](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_AxOpt#12)]  
  
## Siehe auch  
 [MFC\-ActiveX\-Steuerelemente: Optimierung](../mfc/mfc-activex-controls-optimization.md)