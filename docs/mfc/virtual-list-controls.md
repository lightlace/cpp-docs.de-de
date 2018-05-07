---
title: Virtuelle Listensteuerelemente | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- cache, virtual list control item data
- list controls [MFC], virtual
- list controls [MFC], List view
- virtual list controls
ms.assetid: 319f841f-e426-423a-8276-d93f965b0b45
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0b580e455aab7ff95beb85c02b8e3ca79dfa8a46
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="virtual-list-controls"></a>Virtuelle Listensteuerelemente
Ein virtuelles Listensteuerelement ist ein Listenansicht-Steuerelement, das verfügt die **LVS_OWNERDATA** Stil. Dieser Stil aktiviert das Steuerelement eine Elementanzahl bis zu unterstützen eine `DWORD` (standardelementanzahl nur erstreckt sich auch auf eine `int`). Der größte Vorteil von diesem Format bereitgestellt ist jedoch die Möglichkeit, nur eine Teilmenge der Daten im Arbeitsspeicher gleichzeitig. Dadurch können virtuelle Listenansicht-Steuerelement, für die Verwendung mit großen Datenbanken Informationstypen, verleiten bestimmte Methoden zum Zugreifen auf Daten, auf dem bereits vorhanden sind.  
  
> [!NOTE]
>  Zusätzlich zur Bereitstellung der Liste der virtuellen Funktionen in `CListCtrl`, MFC bietet auch die gleiche Funktionalität in der [CListView](../mfc/reference/clistview-class.md) Klasse.  
  
 Es gibt einige Kompatibilitätsprobleme, die Sie beim Entwickeln von virtuelle Listensteuerelemente beachten sollten. Weitere Informationen finden Sie unter der Kompatibilitätsprobleme-Abschnitt des Themas Listenansicht Steuerelemente im Windows SDK.  
  
## <a name="handling-the-lvngetdispinfo-notification"></a>Behandeln der LVN_GETDISPINFO-Benachrichtigung  
 Virtuelle Listensteuerelemente verwalten sehr wenig Informationen. Alle Elementinformationen wird mit Ausnahme der Elementauswahl und den Fokus vom Besitzer des Steuerelements verwaltet. Informationen angefordert wird, durch das Framework über eine **LVN_GETDISPINFO** Benachrichtigung. Um die angeforderten Informationen zu gewährleisten, muss der Besitzer der virtuellen Listensteuerelement (oder das Steuerelement selbst) diese Benachrichtigung behandeln. Dies kann problemlos erfolgen mithilfe des Eigenschaftenfensters (finden Sie unter [Zuordnen von Meldungen zu Funktionen](../mfc/reference/mapping-messages-to-functions.md)). Der resultierende Code sollte etwa wie im folgenden Beispiel aussehen (wobei `CMyDialog` besitzt das Steuerelementobjekt Liste der virtuellen und das Dialogfeld "die Benachrichtigung behandelt wird):  
  
 [!code-cpp[NVC_MFCControlLadenDialog#23](../mfc/codesnippet/cpp/virtual-list-controls_1.cpp)]  
  
 Im Handler für das **LVN_GETDISPINFO** Benachrichtigung, die Sie überprüfen müssen, um festzustellen, welche Art von Informationen angefordert werden. Mögliche Werte sind:  
  
-   `LVIF_TEXT` Der `pszText` Member muss ausgefüllt werden.  
  
-   `LVIF_IMAGE` Der `iImage` Member muss ausgefüllt werden.  
  
-   **LVIF_INDENT** der *iIndent* Member muss ausgefüllt werden.  
  
-   `LVIF_PARAM` Die *lParam* Member muss ausgefüllt werden. (Nicht für untergeordnete Elemente vorhanden Sie.)  
  
-   `LVIF_STATE` Die *Zustand* Member muss ausgefüllt werden.  
  
 Sie sollten dann angeben, an das Framework Restinformationen angefordert wird.  
  
 Im folgende Beispiel (stammt aus dem Text der Benachrichtigungshandler für das Steuerelement Listenobjekt) zeigt eine mögliche Methode durch Angabe von Informationen für den Textpuffer und Bild eines Elements:  
  
 [!code-cpp[NVC_MFCControlLadenDialog#24](../mfc/codesnippet/cpp/virtual-list-controls_2.cpp)]  
  
## <a name="caching-and-virtual-list-controls"></a>Zwischenspeichern und virtuelle Listensteuerelemente  
 Da dieser Typ des Steuerelements für große Datasets vorgesehen ist, wird empfohlen, dass Sie die angeforderten Daten zur Verbesserung der Leistung der Abruf Zwischenspeichern. Das Framework bietet einen Mechanismus Cache-Hinweise bei der Optimierung des Caches durch Senden einer **LVN_ODCACHEHINT** Benachrichtigung.  
  
 Das folgende Beispiel aktualisiert den Cache mit dem Bereich an die Handlerfunktion zu übergeben.  
  
 [!code-cpp[NVC_MFCControlLadenDialog#25](../mfc/codesnippet/cpp/virtual-list-controls_3.cpp)]  
  
 Weitere Informationen zum Vorbereiten und verwalten einen Cache finden Sie unter der Cacheverwaltung-Abschnitt des Themas Listenansicht Steuerelemente im Windows SDK.  
  
## <a name="finding-specific-items"></a>Suchen von bestimmten Elementen  
 Die **LVN_ODFINDITEM** Benachrichtigung wird vom virtuellen Listensteuerelement gesendet, wenn einem bestimmten Steuerelement ein Element gefunden werden muss. Die Benachrichtigung wird gesendet, wenn Listenansicht-Steuerelement schnellen Zugriff auf den Schlüssel empfängt oder beim Empfang einer **LVM_FINDITEM** Nachricht. Suchinformationen wird gesendet, in Form von einer **LVFINDINFO** -Struktur, die ein Element ist von der **NMLVFINDITEM** Struktur. Behandeln Sie diese Meldung durch Überschreiben der `OnChildNotify` Funktion in der Liste Objekt zu steuern und überprüfen Sie im Textkörper des ereignishandlers für das **LVN_ODFINDITEM** Nachricht. Wenn gefunden, wird die entsprechende Aktion ausgeführt.  
  
 Sie sollten darauf vorbereitet sein, für ein Element zu suchen, die von der Listenansicht-Steuerelement Informationen übereinstimmt. Sie sollten den Index des Elements, wenn erfolgreich, oder-1 zurück, wenn kein übereinstimmendes Element gefunden wird.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von CListCtrl](../mfc/using-clistctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)

