---
title: Optimieren von Persistenz und Initialisierung | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC ActiveX controls [MFC], optimizing
- performance, ActiveX controls
- optimization, ActiveX controls
- optimizing performance, ActiveX controls
ms.assetid: e821e19e-b9eb-49ab-b719-0743420ba80b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d03966cb61e1ccab3f8f3886638efdf95a534a73
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/25/2018
ms.locfileid: "36930312"
---
# <a name="optimizing-persistence-and-initialization"></a>Optimieren von Persistenz und Initialisierung
Standardmäßig Persistenz und Initialisierung in einem Steuerelement vom gehandhabt werden die `DoPropExchange` Memberfunktion. In einem typischen Steuerelement diese Funktion enthält mehrere Aufrufe **PX_** Funktionen (`PX_Color`, `PX_Font`usw.), eine für jede Eigenschaft.  
  
 Dieser Ansatz hat den Vorteil, ein einzelnes `DoPropExchange` Implementierung kann verwendet werden, für die Initialisierung für den permanenten Speicher im Binärformat und für den permanenten Speicher im so genannten "Eigenschaftenbehälter"-Format, das von einigen Containern verwendet. Diese eine bestimmte Funktion enthält alle Informationen über die Eigenschaften und ihre Standardwerte an einem geeigneten Ort.  
  
 Ist der dieser Allgemeingültigkeit jedoch auf Kosten der Effizienz. Die **PX_** Funktionen Abrufen ihrer Flexibilität durch mehrschichtige Implementierungen, die grundsätzlich weniger effizient sein als eine direktere, aber weniger flexibel Ansätze. Darüber hinaus, wenn ein Steuerelement einen Standardwert, übergibt ein **PX_** -Funktion übergeben wird, diese Standardwert muss jedes Mal bereitgestellt werden, auch in Situationen, wenn der Standardwert nicht unbedingt verwendet werden kann. Wenn das Generieren des Standardwerts ist eine triviale Vorgang (z. B., wenn der Wert einer ambient-Eigenschaft abgerufen wird) und dann zusätzliche, unnötige Arbeit in Fällen erfolgt, in dem der Standardwert nicht verwendet wird.  
  
 Sie können das Steuerelement binäre Dauerhaftigkeit Leistung verbessern, durch Außerkraftsetzen des Steuerelements `Serialize` Funktion. Ruft die standardmäßige Implementierung des diese Memberfunktion auf Ihre `DoPropExchange` Funktion. Durch das Überschreiben dieser können Sie eine direktere Implementierung für die binäre Dauerhaftigkeit bereitstellen. Angenommen, Sie haben diese `DoPropExchange` Funktion:  
  
 [!code-cpp[NVC_MFC_AxOpt#1](../mfc/codesnippet/cpp/optimizing-persistence-and-initialization_1.cpp)]  
  
 Sie können zur Verbesserung der Leistung der binäre Dauerhaftigkeit des Steuerelements überschreiben die `Serialize` -Funktion wie folgt:  
  
 [!code-cpp[NVC_MFC_AxOpt#2](../mfc/codesnippet/cpp/optimizing-persistence-and-initialization_2.cpp)]  
  
 Die `dwVersion` lokale Variable verwendet werden kann, zu erkennen, die Version des persistenten Status des Steuerelements geladen oder gespeichert werden. Sie können diese Variable verwenden, statt [CPropExchange::GetVersion](../mfc/reference/cpropexchange-class.md#getversion).  
  
 Um ein wenig Platz zu sparen, in einem persistenten Format für eine **BOOL** -Eigenschaft (und mit dem Format von erzeugten kompatibel zu halten `PX_Bool`), können Sie die Eigenschaft als Speichern einer **BYTE**wie folgt:  
  
 [!code-cpp[NVC_MFC_AxOpt#3](../mfc/codesnippet/cpp/optimizing-persistence-and-initialization_3.cpp)]  
  
 Beachten Sie, dass im Fall laden eine temporäre Variable wird verwendet, und klicken Sie dann deren Wert zugewiesen wird, anstatt die Umwandlung *M_boolProp* zu einem **BYTE** Verweis. Das Umwandlungsverfahren würde nur ein Byte des *M_boolProp* geändert wird, lassen Sie die restlichen Bytes nicht initialisiert.  
  
 Für das Steuerelement, können Sie das Steuerelement Initialisierung optimieren, indem Sie überschreiben [COleControl:: OnResetState ein](../mfc/reference/colecontrol-class.md#onresetstate) wie folgt:  
  
 [!code-cpp[NVC_MFC_AxOpt#4](../mfc/codesnippet/cpp/optimizing-persistence-and-initialization_4.cpp)]  
  
 Obwohl `Serialize` und `OnResetState` überschrieben wurden, die `DoPropExchange` Funktion sollte intakt gehalten, da er immer noch für den permanenten Speicher, in der Eigenschaftensammlung Format verwendet wird. Es ist wichtig, alle drei dieser Funktionen, um sicherzustellen, dass das Steuerelement seine Eigenschaften konsistent verwaltet zu verwalten, unabhängig davon, welche Persistenz der Container verwendet.  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-ActiveX-Steuerelemente: Optimierung](../mfc/mfc-activex-controls-optimization.md)

