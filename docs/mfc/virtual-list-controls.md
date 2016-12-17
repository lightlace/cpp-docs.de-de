---
title: "Virtuelle Listensteuerelemente"
ms.custom: na
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Cache, virtuelle Listensteuerelementdaten"
  - "List-Steuerelemente, Listenansicht"
  - "List-Steuerelemente, Virtuell"
  - "virtuelle Listensteuerelemente"
ms.assetid: 319f841f-e426-423a-8276-d93f965b0b45
caps.latest.revision: 13
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# Virtuelle Listensteuerelemente
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ein virtuelles Listensteuerelement ist ein ListView\-Steuerelement, das **LVS\_OWNERDATA** Format hat.  Dieses Format wird das Steuerelement aktiviert, um eine Elementanzahl bis `DWORD` zu unterstützen \(die Standardelementanzahl erweitert nur bei `int`\).  Allerdings ist der größte Vorteil, der von diesem Stil bereitgestellt wird, die Möglichkeit, einer Teilmenge Datenelemente im Arbeitsspeicher nur zu jeder Zeit haben.  Dies ermöglicht dem virtuellen ListView\-Steuerelement, die für die Verwendung mit großen Datenbanken von Informationen zu leihen, in denen bestimmte Methoden zum Zugreifen auf Daten bereits gesorgt sind.  
  
> [!NOTE]
>  Neben der virtuellen Listenfunktionalität in `CListCtrl`, MFC stellt auch die gleiche Funktionalität in der Klasse [CListView](../mfc/reference/clistview-class.md).  
  
 Es gibt mehrere Schnittstellen, die Sie beachten sollten, wenn Sie virtuelle Listensteuerelemente entwickeln.  Weitere Informationen finden Sie den Kompatibilitätsproblemabschnitt des Listenansicht\-Steuerelement\-Themas in [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)].  
  
## Behandeln der LVN\_GETDISPINFO\-Benachrichtigung  
 Virtuelle Listensteuerelemente behalten sehr wenig Elementinformationen bei.  Neben der Element\-Auswahl und den Fokuseninformationen werden alle Elementinformationen vom Besitzer des Steuerelements verwaltet.  Informationen werden durch das Framework über eine **LVN\_GETDISPINFO** Benachrichtigung angefordert.  Um die erforderlichen Informationen bereitstellen, müssen der Besitzer des virtuellen Listensteuerelements \(oder das Steuerelement selbst\) diese Benachrichtigung bearbeiten.  Dies kann mithilfe des Eigenschaftenfensters einfach durchgeführt werden \(siehe [Zuordnungs\-Meldungen auf Funktionen](../mfc/reference/mapping-messages-to-functions.md)\).  Der resultierende Code sollte etwa wie das folgende Beispiel aussehen \(wobei `CMyDialog` das Objekt des virtuellen Listensteuerelements besitzt und das Dialogfeld die Benachrichtigung behandelt\):  
  
 [!CODE [NVC_MFCControlLadenDialog#23](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCControlLadenDialog#23)]  
  
 Im Handler für die **LVN\_GETDISPINFO** Benachrichtigung, müssen Sie überprüfen, um anzuzeigen, welcher Typ von Informationen angefordert wird.  Mögliche Werte sind:  
  
-   `LVIF_TEXT` der Member muss `pszText` gefüllt werden.  
  
-   `LVIF_IMAGE` der Member muss `iImage` gefüllt werden.  
  
-   **LVIF\_INDENT** der *iIndent* \-Member muss gefüllt werden.  
  
-   `LVIF_PARAM` der *lParam* \-Member muss gefüllt werden. \(Nicht für Unterelemente vorhanden.\)  
  
-   `LVIF_STATE` der *Zustandsmember*  muss gefüllt werden.  
  
 Sie sollten dann angeben, welche Informationen zurück zum Framework angefordert werden.  
  
 Das folgenden Beispiel \(erstellt aus dem Text des Benachrichtigungshandlers für das Listensteuerelementobjekt\) wird eine andere Methode, indem Informationen für die Textpuffer und das Bild eines Elements angibt:  
  
 [!CODE [NVC_MFCControlLadenDialog#24](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCControlLadenDialog#24)]  
  
## Zwischenspeichern und virtuelle Listensteuerelemente  
 Da dieser Typ des Listensteuerelements für große Datasets vorgesehen ist, wird empfohlen, angeforderte Elementdaten zwischenspeichern, um Abrufleistung zu verbessern.  Das Framework stellt einen Cache\-Andeutungsmechanismus der Vorlage im Optimieren des Cache dem Senden einer Benachrichtigung **LVN\_ODCACHEHINT** bereit.  
  
 Im folgenden Beispiel wird der Cache mit dem Bereich, der an die Handlerfunktion zu übergeben wird.  
  
 [!CODE [NVC_MFCControlLadenDialog#25](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCControlLadenDialog#25)]  
  
 Weitere Informationen zum Vorbereiten und Verwalten eines Cache, finden Sie den Cache\-Verwaltungsabschnitt des Listenansicht\-Steuerelement\-Themas in [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)].  
  
## Suchen bestimmter Elemente  
 **LVN\_ODFINDITEM** Die Benachrichtigung wird vom virtuellen Listensteuerelement gesendet, wenn ein bestimmtes Listensteuerelementelement gefunden werden muss.  Die Benachrichtigung wird gesendet, sofern das ListView\-Steuerelement Kurztastenzugriff empfängt, oder wenn es eine Meldung empfängt. **LVM\_FINDITEM** Sucheninformationen werden in Form einer **LVFINDINFO**\-Struktur gesendet, die ein Member der **NMLVFINDITEM**\-Struktur ist.  Bearbeiten Sie diese Meldung, indem Sie die `OnChildNotify`\-Funktion des Listensteuerelementobjekts und \-inneres der Text des Handlers, überprüfen Sie die Meldung **LVN\_ODFINDITEM** überschreiben.  Wenn Sie gefunden werden, führen Sie die entsprechende Aktion aus.  
  
 Sie sollten darauf vorbereitet sein, für ein Element, das die Informationen übereinstimmt, die durch das ListView\-Steuerelement angegeben werden.  Sie sollten den Index des Elements, wenn erfolgreich oder \-1 zurück, wenn kein entsprechendes Element gefunden wird.  
  
## Siehe auch  
 [Verwenden von CListCtrl](../mfc/using-clistctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)