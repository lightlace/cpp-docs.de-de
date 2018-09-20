---
title: 'Vorgehensweise: Erstellen einer Meldungszuordnung für eine Vorlagenklasse | Microsoft-Dokumentation'
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
ms.openlocfilehash: 4517c2131e3a8825968d287ef7c1f5725721c17a
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46422089"
---
# <a name="how-to-create-a-message-map-for-a-template-class"></a>Gewusst wie: Erstellen einer Meldungszuordnung für eine Vorlagenklasse

Nachrichtenzuordnung in MFC bietet eine effiziente Möglichkeit zum Weiterleiten von Windows-Nachrichten an eine geeignete Instanz des C++-Objekt. Beispiele für MFC-Nachricht Zuordnung Ziele sind Anwendungsklassen, Dokument und Anzeigen von Klassen, Steuerelementklassen und So weiter.

Herkömmliche MFC-meldungszuordnungen deklariert werden, mithilfe der [BEGIN_MESSAGE_MAP](reference/message-map-macros-mfc.md#begin_message_map) Makro, um den Anfang der meldungszuordnung, einen Makro-Eintrag für jede Methode Meldungshandler-Klasse zu deklarieren und schließlich die [END_MESSAGE_MAP](reference/message-map-macros-mfc.md#end_message_map)Makro, um das Ende der nachrichtenzuordnung zu deklarieren.

Eine Einschränkung mit der [BEGIN_MESSAGE_MAP](reference/message-map-macros-mfc.md#begin_message_map) Makro tritt auf, wenn es in Verbindung mit einer Klasse mit Vorlagenargumenten verwendet wird. Bei Verwendung mit einer Vorlagenklasse bewirkt dieses Makro einen Fehler während der Kompilierung aufgrund der fehlenden Vorlagenparametern bei der makroerweiterung. Die [BEGIN_TEMPLATE_MESSAGE_MAP](reference/message-map-macros-mfc.md#begin_template_message_map) Makro wurde konzipiert, ordnet der Klassen, die mit einer einzelnen Template-Argument, um eigene Nachricht zu deklarieren.

## <a name="example"></a>Beispiel

Sehen Sie ein Beispiel, in dem die MFC-Bibliothek [CListBox](../mfc/reference/clistbox-class.md) Klasse wird erweitert, um eine Synchronisierung mit einer externen Datenquelle bereitzustellen. Die fiktive `CSyncListBox` Klasse wird folgendermaßen deklariert:

[!code-cpp[NVC_MFC_CListBox#42](../mfc/codesnippet/cpp/how-to-create-a-message-map-for-a-template-class_1.h)]

Die `CSyncListBox` Klasse ist als Vorlagen für einen einzelnen Typ, die die Datenquelle beschreibt es mit synchronisiert werden. Sie deklariert außerdem drei Methoden, die in der meldungszuordnung der Klasse einbezogen werden: `OnPaint`, `OnDestroy`, und `OnSynchronize`. Die `OnSynchronize` Methode wird folgendermaßen implementiert:

[!code-cpp[NVC_MFC_CListBox#43](../mfc/codesnippet/cpp/how-to-create-a-message-map-for-a-template-class_2.cpp)]

Die oben erwähnte Implementierung ermöglicht die `CSyncListBox` Klasse in einem beliebigen Klasse spezialisiert werden, die implementiert die `GetCount` -Methode, wie z. B. `CArray`, `CList`, und `CMap`. Die `StringizeElement` -Funktion ist eine Vorlagenfunktion, die durch den folgenden Prototyp:

[!code-cpp[NVC_MFC_CListBox#44](../mfc/codesnippet/cpp/how-to-create-a-message-map-for-a-template-class_3.cpp)]

Normalerweise würde wie folgt die meldungszuordnung für diese Klasse definiert werden:

```cpp
BEGIN_MESSAGE_MAP(CSyncListBox, CListBox)
  ON_WM_PAINT()
  ON_WM_DESTROY()
  ON_MESSAGE(LBN_SYNCHRONIZE, OnSynchronize)
END_MESSAGE_MAP()
```

wo **LBN_SYNCHRONIZE** ist eine benutzerdefinierte Nachricht, die von der Anwendung definiert, wie z. B.:

[!code-cpp[NVC_MFC_CListBox#45](../mfc/codesnippet/cpp/how-to-create-a-message-map-for-a-template-class_4.cpp)]

Die oben genannten Makro-Zuordnung wird nicht kompiliert werden, auf der Tatsache, dass die Vorlagenspezifikation für die `CSyncListBox` Klasse ist nicht vorhanden sein, bei der makroerweiterung. Die **BEGIN_TEMPLATE_MESSAGE_MAP** Makro löst dieses Problem durch die Aufnahme von des angegebenen Vorlagenparameter in das erweiterte Makro-Zuordnung. Die meldungszuordnung für diese Klasse wird:

[!code-cpp[NVC_MFC_CListBox#46](../mfc/codesnippet/cpp/how-to-create-a-message-map-for-a-template-class_5.cpp)]

Das folgende Beispiel zeigt, Beispiel für die Verwendung von der `CSyncListBox` -Klasse unter Verwendung einer `CStringList` Objekt:

[!code-cpp[NVC_MFC_CListBox#47](../mfc/codesnippet/cpp/how-to-create-a-message-map-for-a-template-class_6.cpp)]

Zum Ausführen der Tests, die `StringizeElement` Funktion spezialisiert sein muss, um die Arbeit mit der `CStringList` Klasse:

[!code-cpp[NVC_MFC_CListBox#48](../mfc/codesnippet/cpp/how-to-create-a-message-map-for-a-template-class_7.cpp)]

## <a name="see-also"></a>Siehe auch

[BEGIN_TEMPLATE_MESSAGE_MAP](reference/message-map-macros-mfc.md#begin_template_message_map)<br/>
[Meldungsbehandlung und Zuordnung](../mfc/message-handling-and-mapping.md)

