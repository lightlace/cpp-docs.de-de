---
title: OLE-Steuerelementklassen
ms.date: 11/04/2016
f1_keywords:
- vc.classes.ole
helpviewer_keywords:
- ActiveX classes [MFC]
- custom controls [MFC], classes
- ActiveX controls [MFC], OLE control classes
- ActiveX control classes [MFC]
- OLE controls [MFC], classes
- OLE control classes [MFC]
- reusable component classes [MFC]
ms.assetid: 96495ec3-319e-4163-b839-1af0428ed9dd
ms.openlocfilehash: 909da3dc7b4f0298e6e5476ed7716257cc4d101d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50509556"
---
# <a name="ole-control-classes"></a>OLE-Steuerelementklassen

Dies sind die primären Klassen, mit denen Sie beim Schreiben von OLE-Steuerelemente. Die `COleControlModule` Klasse in einem Modul der OLE-Steuerelements ist wie die [CWinApp](../mfc/reference/cwinapp-class.md) Klassen in einer Anwendung. Jedes Modul implementiert ein oder mehrere OLE-Steuerelemente ist. Diese Steuerelemente werden durch dargestellt `COleControl` Objekte. Diese Steuerelemente zu kommunizieren, mit ihren Containern unter Verwendung von `CConnectionPoint` Objekte.

Die `CPictureHolder` und `CFontHolder` Klassen kapseln COM-Schnittstellen für Grafiken und Schriftarten, während die `COlePropertyPage` und `CPropExchange` -Klassen können Sie die Eigenschaftenseiten und Beständigkeit von Eigenschaften für das Steuerelement zu implementieren.

[COleControlModule](../mfc/reference/colecontrolmodule-class.md)<br/>
Ersetzt die `CWinApp` Klasse für das OLE-Steuerelement-Modul. Leiten Sie von der `COleControlModule` Klasse, um ein OLE-Steuerelement-Modul-Objekt zu entwickeln. Es bietet Memberfunktionen zum Initialisieren des OLE-Steuerelements-Modul.

[COleControl](../mfc/reference/colecontrol-class.md)<br/>
Leiten Sie von der `COleControl` Klasse, um die Entwicklung eines OLE-Steuerelements. Abgeleitet von `CWnd`, diese Klasse erbt die gesamte Funktionalität von einem Windows-Fensterobjekt und zusätzliche OLE-spezifische Funktionen, z. B. das Auslösen von Ereignissen und die Möglichkeit, Methoden und Eigenschaften zu unterstützen.

[CConnectionPoint](../mfc/reference/cconnectionpoint-class.md)<br/>
Die `CConnectionPoint` Klasse definiert eine besondere Art von Schnittstelle zur Kommunikation mit anderen OLE-Objekte, die einen Verbindungspunkt aufgerufen. Ein Verbindungspunkt implementiert eine ausgehende-Schnittstelle, die zum Initiieren von Aktionen auf andere Objekte, z. B. das Auslösen von Ereignissen und Benachrichtigungen ändern kann.

[CPictureHolder](../mfc/reference/cpictureholder-class.md)<br/>
Kapselt die Funktionalität eines Windows-Bildobjekts und der `IPicture` COM-Schnittstelle verwendet, um die benutzerdefinierte Bildeigenschaft eines OLE-Steuerelements zu implementieren.

[CFontHolder](../mfc/reference/cfontholder-class.md)<br/>
Kapselt die Funktionalität eines Windows-Schriftartobjekts und der `IFont` COM-Schnittstelle verwendet, um die vordefinierte Schriftarteigenschaft eines OLE-Steuerelements zu implementieren.

[COlePropertyPage](../mfc/reference/colepropertypage-class.md)<br/>
Zeigt steuern Sie die Eigenschaften von einer OLE in eine grafische Oberfläche, ähnlich wie ein Dialogfeld.

[CPropExchange](../mfc/reference/cpropexchange-class.md)<br/>
Die Implementierung der Dauerhaftigkeit der Eigenschaft unterstützt für die OLE-Steuerelemente. Analog zu [CDataExchange](../mfc/reference/cdataexchange-class.md) für Dialogfelder.

[CMonikerFile](../mfc/reference/cmonikerfile-class.md)<br/>
Erfordert einen Moniker oder eine Zeichenfolgendarstellung, der an einen Moniker kann, und bindet sie in den Stream für den der Moniker ein Name ist synchron.

[CAsyncMonikerFile](../mfc/reference/casyncmonikerfile-class.md)<br/>
Ähnliche Funktionsweise wie `CMonikerFile`jedoch bindet den Moniker asynchron in den Stream für die der Moniker ein Name ist.

[CDataPathProperty](../mfc/reference/cdatapathproperty-class.md)<br/>
Implementiert eine OLE-Steuerelementeigenschaft, die asynchron geladen werden kann.

[CCachedDataPathProperty](../mfc/reference/ccacheddatapathproperty-class.md)<br/>
Implementiert eine asynchron übertragene und in einer Arbeitsspeicherdatei zwischengespeicherte OLE-Steuerelementeigenschaft.

[COleCmdUI](../mfc/reference/colecmdui-class.md)<br/>
Ermöglicht ein aktiven Dokuments um Befehle zu empfangen, die in der zugehörigen Containers-Benutzeroberfläche (z. B. FileNew, Open, Print und So weiter) stammen, und einen Container aus, um Befehle zu empfangen, die in der Benutzeroberfläche für das aktive Dokument stammen.

[COleSafeArray](../mfc/reference/colesafearray-class.md)<br/>
Funktioniert mit Arrays von Dimension und beliebigen Typs.

## <a name="see-also"></a>Siehe auch

[Übersicht über die Klasse](../mfc/class-library-overview.md)

