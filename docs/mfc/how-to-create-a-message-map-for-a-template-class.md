---
title: 'Vorgehensweise: erstellen eine Meldungszuordnung für eine Vorlagenklasse | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- template classes [MFC], creating message maps
- message maps [MFC], template classes
ms.assetid: 4e7e24f8-06df-4b46-82aa-7435c8650de3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f7867cc40ae837da5fad957b6a1d584fb7c2c4ce
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/25/2018
ms.locfileid: "36929899"
---
# <a name="how-to-create-a-message-map-for-a-template-class"></a>Gewusst wie: Erstellen einer Meldungszuordnung für eine Vorlagenklasse
Nachrichtenzuordnung in MFC bietet eine effiziente Möglichkeit zum Weiterleiten von Windows-Nachrichten an eine Instanz des entsprechenden C++. Beispiele für MFC-Nachricht Zuordnung Ziele sind Anwendungsklassen, Dokument und Ansicht-Klassen, Klassen usw. an.  
  
 Herkömmliche MFC-meldungszuordnungen deklariert werden, mithilfe der [BEGIN_MESSAGE_MAP](reference/message-map-macros-mfc.md#begin_message_map) Makro, das den Anfang der meldungszuordnung, einen Makro-Eintrag für jede Methode Meldungshandler Klasse deklarieren und schließlich die [END_MESSAGE_MAP](reference/message-map-macros-mfc.md#end_message_map)Makro, um das Ende der meldungszuordnung zu deklarieren.  
  
 Eine Einschränkung mit der [BEGIN_MESSAGE_MAP](reference/message-map-macros-mfc.md#begin_message_map) Makro tritt auf, wenn es in Verbindung mit einer Klasse, die Vorlagenargumente enthält verwendet wird. Bei Verwendung in einer Vorlagenklasse bewirkt dieses Makro einen Fehler während der Kompilierung aufgrund der fehlenden Vorlagenparameter bei der makroerweiterung. Die [BEGIN_TEMPLATE_MESSAGE_MAP](reference/message-map-macros-mfc.md#begin_template_message_map) Makro wurde so konzipiert, dass Klassen mit einer einzelnen Vorlagenargument, um eigene Nachricht deklarieren zugeordnet.  
  
## <a name="example"></a>Beispiel  
 Betrachten Sie ein Beispiel, in dem die MFC-Bibliothek [CListBox](../mfc/reference/clistbox-class.md) Klasse wird erweitert, um eine Synchronisierung mit einer externen Datenquelle bereitzustellen. Die fiktive `CSyncListBox` Klasse wird folgendermaßen deklariert:  
  
 [!code-cpp[NVC_MFC_CListBox#42](../mfc/codesnippet/cpp/how-to-create-a-message-map-for-a-template-class_1.h)]  
  
 Die `CSyncListBox` Klasse ist als Vorlagen für einen einzigen Typ, der die Datenquelle führt die Synchronisierung beschreibt mit. Es deklariert auch drei Methoden, die in der Klasse die meldungszuordnung einbezogen werden: `OnPaint`, `OnDestroy`, und `OnSynchronize`. Die `OnSynchronize` Methode wird wie folgt implementiert:  
  
 [!code-cpp[NVC_MFC_CListBox#43](../mfc/codesnippet/cpp/how-to-create-a-message-map-for-a-template-class_2.cpp)]  
  
 Die oben erwähnte Implementierung ermöglicht die `CSyncListBox` Klasse für alle Klassentyp einheitlich spezialisiert behandelt, die implementiert die `GetCount` -Methode, wie z. B. `CArray`, `CList`, und `CMap`. Die `StringizeElement` Funktion wird eine Vorlagenfunktion, die durch den folgenden Prototyp:  
  
 [!code-cpp[NVC_MFC_CListBox#44](../mfc/codesnippet/cpp/how-to-create-a-message-map-for-a-template-class_3.cpp)]  
  
 Normalerweise würde die meldungszuordnung für diese Klasse wie folgt definiert werden:  
  
 `BEGIN_MESSAGE_MAP(CSyncListBox, CListBox)`  
  
 `ON_WM_PAINT()`  
  
 `ON_WM_DESTROY()`  
  
 `ON_MESSAGE(LBN_SYNCHRONIZE, OnSynchronize)`  
  
 `END_MESSAGE_MAP()`  
  
 wobei **LBN_SYNCHRONIZE** ist eine benutzerdefinierte Nachricht, die von der Anwendung definiert, wie z. B.:  
  
 [!code-cpp[NVC_MFC_CListBox#45](../mfc/codesnippet/cpp/how-to-create-a-message-map-for-a-template-class_4.cpp)]  
  
 Die oben genannten Makro-Zuordnung wird nicht kompiliert werden, auf der Tatsache, dass die Vorlagenspezifikation für die `CSyncListBox` Klasse werden bei der makroerweiterung fehlt. Die **BEGIN_TEMPLATE_MESSAGE_MAP** Makro löst dieses Problem durch den angegebenen Vorlagenparameter in das erweiterte Makro Zuordnung einbinden. Die meldungszuordnung für diese Klasse wird:  
  
 [!code-cpp[NVC_MFC_CListBox#46](../mfc/codesnippet/cpp/how-to-create-a-message-map-for-a-template-class_5.cpp)]  
  
 Das folgende Beispiel zeigt die Verwendung des des Beispiels die `CSyncListBox` -Klasse unter Verwendung einer `CStringList` Objekt:  
  
 [!code-cpp[NVC_MFC_CListBox#47](../mfc/codesnippet/cpp/how-to-create-a-message-map-for-a-template-class_6.cpp)]  
  
 Zum Abschließen des Tests die `StringizeElement` Funktion spezialisiert sein muss, für die Zusammenarbeit mit der `CStringList` Klasse:  
  
 [!code-cpp[NVC_MFC_CListBox#48](../mfc/codesnippet/cpp/how-to-create-a-message-map-for-a-template-class_7.cpp)]  
  
## <a name="see-also"></a>Siehe auch  
 [BEGIN_TEMPLATE_MESSAGE_MAP](reference/message-map-macros-mfc.md#begin_template_message_map)   
 [Meldungsbehandlung und Zuordnung](../mfc/message-handling-and-mapping.md)

