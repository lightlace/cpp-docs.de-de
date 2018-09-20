---
title: Verwenden der CArchive &lt; &lt; und &gt; &gt; Operatoren | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- CArchive
dev_langs:
- C++
helpviewer_keywords:
- objects [MFC], loading from previously stored values
- CArchive class [MFC], storing and loading objects
- CArchive class [MFC], operators
ms.assetid: 56aef326-02dc-4992-8282-f0a4b78a064e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 49ea94258c163c241243934f41d55d896d0d1fa2
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46372456"
---
# <a name="using-the-carchive-ltlt-and-gtgt-operators"></a>Verwenden der CArchive &lt; &lt; und &gt; &gt; Operatoren

`CArchive` Stellt <\< und >> Operatoren zum Schreiben und Lesen von einfachen Datentypen sowie `CObject`s in und aus einer Datei.

#### <a name="to-store-an-object-in-a-file-via-an-archive"></a>Ein Objekt in einer Datei per Archiv speichern

1. Das folgende Beispiel zeigt, wie ein Objekt in eine Datei per Archiv gespeichert wird:

     [!code-cpp[NVC_MFCSerialization#7](../mfc/codesnippet/cpp/using-the-carchive-output-and-input-operators_1.cpp)]

#### <a name="to-load-an-object-from-a-value-previously-stored-in-a-file"></a>Laden Sie ein Objekt aus einem Wert, der zuvor in einer Datei gespeichert.

1. Das folgende Beispiel zeigt, wie Sie ein Objekt aus einem Wert, der zuvor in einer Datei gespeicherten zu laden:

     [!code-cpp[NVC_MFCSerialization#8](../mfc/codesnippet/cpp/using-the-carchive-output-and-input-operators_2.cpp)]

In der Regel speichern und Laden Sie Daten in und aus einer Datei mithilfe eines Archivs in die `Serialize` Funktionen `CObject`-abgeleiteten Klassen, die Sie mit dem Makro DECLARE_SERIALIZE deklarieren deklariert haben müssen. Ein Verweis auf eine `CArchive` Objekt übergeben wird, um Ihre `Serialize` Funktion. Rufen Sie die `IsLoading` Funktion der `CArchive` Objekt, um zu bestimmen, ob die `Serialize` Funktion aufgerufen wurde, um Daten aus der Datei zu laden oder Speichern von Daten in die Datei.

Die `Serialize` Funktion ein serialisierbares `CObject`-abgeleiteten Klasse in der Regel weist folgende Form:

[!code-cpp[NVC_MFCSerialization#9](../mfc/codesnippet/cpp/using-the-carchive-output-and-input-operators_3.cpp)]

Die oben genannten Codevorlage ist identisch mit der AppWizard erstellt wird, für die `Serialize` Funktion des Dokuments (eine abgeleitete Klasse `CDocument`). Diese Codevorlage können Sie Code schreiben, der einfacher zu lesen, da der Code zum Speichern und Laden von Code immer parallel, wie im folgenden Beispiel werden soll:

[!code-cpp[NVC_MFCSerialization#10](../mfc/codesnippet/cpp/using-the-carchive-output-and-input-operators_4.cpp)]

Die Bibliothek definiert **< \<** und **>>** Operatoren für `CArchive` als den ersten Operanden und den folgenden Datentypen und Klassentypen als der zweite Operand :

||||
|-|-|-|
|`CObject*`|**Größe** und `CSize`|**float**|
|**WORD**|`CString`|**Punkt** und `CPoint`|
|`DWORD`|**BYTE**|`RECT` und `CRect`|
|**Double**|**LONG**|`CTime` und `CTimeSpan`|
|`Int`|**COleCurrency**|`COleVariant`|
|`COleDateTime`|`COleDateTimeSpan`||

> [!NOTE]
>  Speichern und laden `CObject`über ein Archiv erfordert zusätzlich ist zu berücksichtigen. Weitere Informationen finden Sie unter [speichern und Laden eines CObject per Archiv](../mfc/storing-and-loading-cobjects-via-an-archive.md).

Die **CArchive <\<**  und **>>** Operatoren jederzeit einen Verweis auf die `CArchive` Objekt, das den ersten Operanden ist. Dadurch können Sie die Operatoren verketten, wie unten gezeigt:

[!code-cpp[NVC_MFCSerialization#11](../mfc/codesnippet/cpp/using-the-carchive-output-and-input-operators_5.cpp)]

## <a name="see-also"></a>Siehe auch

[Serialisierung: Serialisieren eines Objekts](../mfc/serialization-serializing-an-object.md)

