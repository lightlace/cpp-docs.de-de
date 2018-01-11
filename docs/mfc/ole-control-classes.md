---
title: OLE-Steuerelementklassen | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.classes.ole
dev_langs: C++
helpviewer_keywords:
- ActiveX classes [MFC]
- custom controls [MFC], classes
- ActiveX controls [MFC], OLE control classes
- ActiveX control classes [MFC]
- OLE controls [MFC], classes
- OLE control classes [MFC]
- reusable component classes [MFC]
ms.assetid: 96495ec3-319e-4163-b839-1af0428ed9dd
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e61d0ca8ed269557efbd566da1aca160ef669e83
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="ole-control-classes"></a>OLE-Steuerelementklassen
Dies sind die primären Klassen, die Sie beim Schreiben von OLE-Steuerelemente verwenden. Die `COleControlModule` Klasse in einem Modul der OLE-Steuerelements ist vergleichbar mit der [CWinApp](../mfc/reference/cwinapp-class.md) Klassen in einer Anwendung. Jedes Modul implementiert ein oder mehrere OLE-Steuerelemente. Diese Steuerelemente werden durch dargestellt `COleControl` Objekte. Diese Steuerelemente mit ihren Container mit kommunizieren `CConnectionPoint` Objekte.  
  
 Die `CPictureHolder` und `CFontHolder` Klassen kapseln, COM-Schnittstellen für Bilder und Schriftarten, während die `COlePropertyPage` und `CPropExchange` -Klassen können Sie die Eigenschaftenseiten und Beständigkeit für das Steuerelement zu implementieren.  
  
 [COleControlModule](../mfc/reference/colecontrolmodule-class.md)  
 Ersetzt die `CWinApp` Klasse für das OLE-Steuerelement-Modul. Ableiten von der `COleControlModule` Klasse zum Entwickeln von OLE-Steuerelement-Modul-Objekt. Memberfunktionen bereitgestellt beim Initialisieren des Moduls für die OLE-Steuerelements.  
  
 [COleControl](../mfc/reference/colecontrol-class.md)  
 Ableiten von der `COleControl` Klasse zum Entwickeln von OLE-Steuerelements. Abgeleitet von `CWnd`, diese Klasse erbt alle die Funktionalität von einem Windows-Fensterobjekt und zusätzliche OLE-spezifische Funktionen, z. B. das Auslösen von Ereignissen und die Fähigkeit zur Unterstützung von Methoden und Eigenschaften.  
  
 [CConnectionPoint](../mfc/reference/cconnectionpoint-class.md)  
 Die `CConnectionPoint` Klasse definiert einen besonderen Schnittstellentyp, der für die Kommunikation mit anderen OLE-Objekten, die einen Verbindungspunkt genannt verwendet. Ein Verbindungspunkt implementiert eine Ausgangsschnittstelle, das Initiieren von Aktionen auf andere Objekte, z. B. das Auslösen von Ereignissen und Benachrichtigungen ändern können.  
  
 [CPictureHolder](../mfc/reference/cpictureholder-class.md)  
 Kapselt die Funktionalität eines Windows-Bildobjekts und der `IPicture` COM-Schnittstelle verwendet, um die benutzerdefinierte Bildeigenschaft eines OLE-Steuerelements zu implementieren.  
  
 [CFontHolder](../mfc/reference/cfontholder-class.md)  
 Kapselt die Funktionalität eines Windows-Schriftartobjekts und der `IFont` COM-Schnittstelle verwendet, um die vordefinierte Schriftarteigenschaft eines OLE-Steuerelements zu implementieren.  
  
 [COlePropertyPage](../mfc/reference/colepropertypage-class.md)  
 Zeigt die Eigenschaften des OLE in einer grafischen Oberfläche, ähnlich wie in einem Dialogfeld zu steuern.  
  
 [CPropExchange](../mfc/reference/cpropexchange-class.md)  
 Unterstützt die Implementierung der Dauerhaftigkeit der Eigenschaft für die OLE-Steuerelemente. Analog zu [CDataExchange](../mfc/reference/cdataexchange-class.md) für Dialogfelder.  
  
 [CMonikerFile](../mfc/reference/cmonikerfile-class.md)  
 Erfordert ein Moniker oder eine Zeichenfolgendarstellung, die es in ein Moniker vornehmen können, und bindet sie synchron in den Stream für den Moniker ein Name ist.  
  
 [CAsyncMonikerFile](../mfc/reference/casyncmonikerfile-class.md)  
 Funktioniert ähnlich wie `CMonikerFile`, aber es bindet den Moniker asynchron in den Stream, der für die ist der Moniker einen Namen.  
  
 [CDataPathProperty](../mfc/reference/cdatapathproperty-class.md)  
 Implementiert eine OLE-Steuerelementeigenschaft, die asynchron geladen werden kann.  
  
 [CCachedDataPathProperty](../mfc/reference/ccacheddatapathproperty-class.md)  
 Implementiert eine asynchron übertragene und in einer Arbeitsspeicherdatei zwischengespeicherte OLE-Steuerelementeigenschaft.  
  
 [COleCmdUI](../mfc/reference/colecmdui-class.md)  
 Ein aktiven Dokuments ein, um Befehle zu empfangen, die in den Container-Benutzeroberfläche (z. B. FileNew, öffnen, drucken usw.) stammen, und einen Container, um Befehle zu empfangen, die in der Benutzeroberfläche für das aktive Dokument stammen.  
  
 [COleSafeArray](../mfc/reference/colesafearray-class.md)  
 Funktioniert mit Arrays beliebiger Dimension und beliebigen Typs.  
  
## <a name="see-also"></a>Siehe auch  
 [Klassenübersicht](../mfc/class-library-overview.md)

