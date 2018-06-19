---
title: Verwenden der CArchive &lt; &lt; und &gt; &gt; Operatoren | Microsoft Docs
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
ms.openlocfilehash: 82b729caaa650fde72741497d3f4ab3c131f46ab
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33383331"
---
# <a name="using-the-carchive-ltlt-and-gtgt-operators"></a>Verwenden der CArchive &lt; &lt; und &gt; &gt; Operatoren
`CArchive` bietet <\< und >> Operatoren zum Schreiben und Lesen von einfachen Datentypen sowie `CObject`s in und aus einer Datei.  
  
#### <a name="to-store-an-object-in-a-file-via-an-archive"></a>Um ein Objekt in eine Datei per Archiv speichern  
  
1.  Im folgende Beispiel wird gezeigt, wie ein Objekt in eine Datei per Archiv gespeichert wird:  
  
     [!code-cpp[NVC_MFCSerialization#7](../mfc/codesnippet/cpp/using-the-carchive-output-and-input-operators_1.cpp)]  
  
#### <a name="to-load-an-object-from-a-value-previously-stored-in-a-file"></a>Laden Sie ein Objekt aus einem Wert, der zuvor in einer Datei gespeichert.  
  
1.  Das folgende Beispiel zeigt, wie ein Objekt aus einem zuvor in einer Datei gespeicherten Wert geladen wird:  
  
     [!code-cpp[NVC_MFCSerialization#8](../mfc/codesnippet/cpp/using-the-carchive-output-and-input-operators_2.cpp)]  
  
 In der Regel zu speichern und Laden von Daten in und aus einer Datei per Archiv in dem `Serialize` Funktionen `CObject`-abgeleiteten Klassen, die Sie mit deklariert haben, müssen die **DECLARE_SERIALIZE deklarieren** Makro. Ein Verweis auf eine `CArchive` -Objekt übergeben wird Ihre `Serialize` Funktion. Rufen Sie die `IsLoading` Funktion der `CArchive` Objekt, um zu bestimmen, ob die `Serialize` Funktion aufgerufen wurde, um das Laden von Daten aus der Datei oder Speichern von Daten in die Datei.  
  
 Die `Serialize` Funktion ein serialisierbares `CObject`-abgeleitete Klasse hat normalerweise das folgende Format:  
  
 [!code-cpp[NVC_MFCSerialization#9](../mfc/codesnippet/cpp/using-the-carchive-output-and-input-operators_3.cpp)]  
  
 Die oben genannten Codevorlage entspricht dem die Woche AppWizard, für erstellt die `Serialize` Funktion des Dokuments (eine abgeleitete Klasse **CDocument)**. Dieser Codevorlage können Sie Code schreiben, die einfacher zu lesen, da der Code zum Speichern und den Code zum Laden immer parallel, wie im folgenden Beispiel werden sollen:  
  
 [!code-cpp[NVC_MFCSerialization#10](../mfc/codesnippet/cpp/using-the-carchive-output-and-input-operators_4.cpp)]  
  
 Die Bibliothek definiert **< \<** und **>>** Operatoren für `CArchive` als der erste Operand und die folgenden Datentypen und Klassentypen als zweiter Operand :  
  
||||  
|-|-|-|  
|`CObject*`|**Größe und CSize**|**float**|  
|**WORD**|`CString`|**Zeigen Sie** und `CPoint`|  
|`DWORD`|**BYTE**|`RECT` und `CRect`|  
|**Double**|**LONG**|`CTime` und `CTimeSpan`|  
|`Int`|**COleCurrency**|`COleVariant`|  
|`COleDateTime`|`COleDateTimeSpan`||  
  
> [!NOTE]
>  Speichern und Laden von `CObject`s per Archiv muss zusätzliche berücksichtigt werden. Weitere Informationen finden Sie unter [speichern und Laden eines CObject per Archiv](../mfc/storing-and-loading-cobjects-via-an-archive.md).  
  
 Die **CArchive <\<**  und **>>** Operatoren stets einen Verweis auf die `CArchive` Objekt, das den ersten Operanden ist. Dadurch können Sie die Operatoren verketten, wie unten gezeigt:  
  
 [!code-cpp[NVC_MFCSerialization#11](../mfc/codesnippet/cpp/using-the-carchive-output-and-input-operators_5.cpp)]  
  
## <a name="see-also"></a>Siehe auch  
 [Serialisierung: Serialisieren eines Objekts](../mfc/serialization-serializing-an-object.md)

