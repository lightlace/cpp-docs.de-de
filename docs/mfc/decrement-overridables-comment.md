---
title: --Overridables-Kommentar
ms.date: 11/04/2016
helpviewer_keywords:
- Overridables comment in MFC source files
- MFC source files, Overridables comment
- overriding, Overridables comment in MFC source files
- comments, MFC
ms.assetid: 8968dea5-0d94-451f-bcb2-991580e65ba2
ms.openlocfilehash: 9efba74676ba118659601522fc915bf25f607116
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50554159"
---
# <a name="-overridables-comment"></a>// Overridables-Kommentar

Die `// Overridables` Teil einer MFC-Klassendeklaration enthält virtuelle Funktionen, die Sie in einer abgeleiteten Klasse überschreiben können, wenn Sie das Verhalten des Basis-Klasse ändern müssen. Sie werden in der Regel mit dem Namen beginnend mit "On", obwohl dies nicht unbedingt erforderlich ist. Hier Funktionen dienen der außer Kraft gesetzt werden, und häufig zu implementieren oder geben Sie eine Art "Callback" oder "verknüpfen". In der Regel sind diese Elemente geschützt.

In MFC selbst sind reine virtuelle Funktionen immer in diesem Abschnitt platziert. Eine reine virtuelle Funktion in C++ ist eine der Form:

`virtual void OnDraw( ) = 0;`

In diesem Beispiel aus der Klasse auflisten `CStdioFile`im [ein Beispiel für die Kommentare](../mfc/an-example-of-the-comments.md), die Liste enthält keine / / Overridables-Abschnitt. Klasse `CDocument`, listet Sie auf der anderen Seite ungefähr 10 überschreibbare Memberfunktionen.

In einigen Klassen, Sie sehen möglicherweise auch den Kommentar `// Advanced Overridables`. Hierbei handelt es sich um Funktionen, die nur von erfahrenen Programmierern versuchen soll, eine Verbindung zu überschreiben. Sie benötigen wahrscheinlich nie um sie zu überschreiben.

> [!NOTE]
>  Die Konventionen, die in diesem Artikel beschriebenen funktionieren auch gut, im Allgemeinen für Automation (früher als OLE-Automatisierung) Methoden und Eigenschaften. Automatisierungsmethoden ähneln MFC-Vorgänge. Automatisierungseigenschaften ähneln MFC-Attribute. Benutzeroberflächenautomatisierungs-Ereignissen (unterstützt für ActiveX-Steuerelemente, früher bekannt als OLE-Steuerelemente) ähneln MFC überschreibbare Memberfunktionen.

## <a name="see-also"></a>Siehe auch

[Verwenden der MFC-Quelldateien](../mfc/using-the-mfc-source-files.md)<br/>
[Ein Beispiel für die Kommentare](../mfc/an-example-of-the-comments.md)<br/>
[/ / Implementierungskommentar](../mfc/decrement-implementation-comment.md)<br/>
[/ Constructors-Kommentar](../mfc/decrement-constructors-comment.md)<br/>
[Attributekommentar](../mfc/decrement-attributes-comment.md)<br/>
[Vorgänge-Kommentar](../mfc/decrement-operations-comment.md)

