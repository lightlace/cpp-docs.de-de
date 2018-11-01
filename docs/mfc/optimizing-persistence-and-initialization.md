---
title: Optimieren von Persistenz und Initialisierung
ms.date: 11/04/2016
helpviewer_keywords:
- MFC ActiveX controls [MFC], optimizing
- performance, ActiveX controls
- optimization, ActiveX controls
- optimizing performance, ActiveX controls
ms.assetid: e821e19e-b9eb-49ab-b719-0743420ba80b
ms.openlocfilehash: 6f0d888f49cf27505882e89e3cdbb469ea9e8684
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50472695"
---
# <a name="optimizing-persistence-and-initialization"></a>Optimieren von Persistenz und Initialisierung

Standardmäßig, Persistenz und Initialisierung in einem Steuerelement werden anhand der `DoPropExchange` Member-Funktion. In einem typischen-Steuerelement, diese Funktion enthält mehrere Aufrufe **PX_** Funktionen (`PX_Color`, `PX_Font`und so weiter), eine für jede Eigenschaft.

Dieser Ansatz hat den Vorteil, ein einzelnes `DoPropExchange` Implementierung kann für die Initialisierung für die Persistenz im Binärformat und Persistenz in der so genannten "Eigenschaftenbehälter"-Format, das einige Container verwendet werden. Diese Funktion eine bietet alle Informationen über die Eigenschaften und ihre Standardwerte an einem zentralen Ort.

Allerdings erfordert diese Allgemeingültigkeit auf Kosten der Effizienz. Die **PX_** Funktionen erhalten ihre Flexibilität durch mehrschichtigen Implementierungen, die grundsätzlich weniger effizient als direktere, aber weniger flexibel, Ansätze. Darüber hinaus, wenn ein Steuerelement einen Standardwert, übergibt ein **PX_** funktionieren, Standardwert muss bereitgestellt werden jedes Mal, auch in Situationen, in denen der Wert nicht unbedingt verwendet werden kann. Wenn das Generieren des Standardwerts ist, eine nicht triviale Aufgabe bevor (z. B., wenn der Wert aus der ambient-Eigenschaft abgerufen wird), und dann zusätzliche, unnötige Arbeit in Fällen erfolgt, in dem der Standardwert nicht verwendet wird.

Können Sie Ihres Steuerelements binäre Persistenz-Leistung verbessern, durch das Überschreiben des Steuerelements `Serialize` Funktion. Die Standardimplementierung von dieser Memberfunktion führt einen Aufruf an Ihre `DoPropExchange` Funktion. Durch das Überschreiben dieser können Sie eine bessere Implementierung für binäre Persistenz bereitstellen. Betrachten Sie beispielsweise diese `DoPropExchange` Funktion:

[!code-cpp[NVC_MFC_AxOpt#1](../mfc/codesnippet/cpp/optimizing-persistence-and-initialization_1.cpp)]

Um die Leistung des binären Persistenz dieses Steuerelements zu verbessern, können Sie überschreiben die `Serialize` -Funktion wie folgt:

[!code-cpp[NVC_MFC_AxOpt#2](../mfc/codesnippet/cpp/optimizing-persistence-and-initialization_2.cpp)]

Die `dwVersion` lokale Variable verwendet werden kann, erkennen die Version der persistente Zustand des Steuerelements geladen oder gespeichert werden. Sie können diese Variable verwenden, statt [CPropExchange::GetVersion](../mfc/reference/cpropexchange-class.md#getversion).

Um ein wenig Platz zu sparen, in den persistenten Format für eine **"bool"** Eigenschaft (und es mit dem Format erzeugten kompatibel `PX_Bool`), können Sie die Eigenschaft als speichern eine **BYTE**wie folgt:

[!code-cpp[NVC_MFC_AxOpt#3](../mfc/codesnippet/cpp/optimizing-persistence-and-initialization_3.cpp)]

Beachten Sie, dass im Fall laden eine temporäre Variable wird verwendet, und klicken Sie dann der Wert zugewiesen wird, anstatt die Umwandlung *M_boolProp* zu einem **BYTE** Verweis. Die Umwandlung-Methode würde nur ein Byte *M_boolProp* geändert wird, lassen Sie die restlichen Bytes, die nicht initialisiert.

Sie können die Initialisierung des Steuerelements durch Überschreiben optimieren, für das gleiche Steuerelement, [COleControl:: OnResetState ein](../mfc/reference/colecontrol-class.md#onresetstate) wie folgt:

[!code-cpp[NVC_MFC_AxOpt#4](../mfc/codesnippet/cpp/optimizing-persistence-and-initialization_4.cpp)]

Obwohl `Serialize` und `OnResetState` überschrieben wurden, die `DoPropExchange` Funktion sollte intakt gehalten, da sie immer noch für die Persistenz im Eigenschaftenbehälter Format verwendet wird. Es ist wichtig, alle drei dieser Funktionen, um sicherzustellen, dass das Steuerelement seine Eigenschaften konsistent und verwaltet, unabhängig von der Persistenz der Container verwendet, zu verwalten.

## <a name="see-also"></a>Siehe auch

[MFC-ActiveX-Steuerelemente: Optimierung](../mfc/mfc-activex-controls-optimization.md)

