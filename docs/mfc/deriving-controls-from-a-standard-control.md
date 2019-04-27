---
title: Ableiten von Steuerelementen von einem Standardsteuerelement
ms.date: 11/04/2016
helpviewer_keywords:
- standard controls [MFC], deriving controls from
- common controls [MFC], deriving from
- derived controls
- controls [MFC], derived
- Windows common controls [MFC], deriving from
- standard controls
ms.assetid: a6f84315-7007-4e0e-8576-78be81254802
ms.openlocfilehash: 5abdcc87dba937938ffa3643d19ff69431f62af4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62206943"
---
# <a name="deriving-controls-from-a-standard-control"></a>Ableiten von Steuerelementen von einem Standardsteuerelement

Wie bei allen [CWnd](../mfc/reference/cwnd-class.md)-abgeleitete Klasse sein, Sie können Verhalten eines Steuerelements ändern, indem Sie eine neue Klasse von einer vorhandenen Steuerelementklasse ableiten.

### <a name="to-create-a-derived-control-class"></a>So erstellen Sie eine abgeleitete Steuerelement-Klasse

1. Leiten Sie eine Klasse von einer vorhandenen Steuerelementklasse, und optional außer Kraft setzen der `Create` Memberfunktion so, dass es sich um die erforderlichen Argumente, die die Basisklasse bietet `Create` Funktion.

1. Geben Sie Meldungshandler-Memberfunktionen und Meldungszuordnungseinträge so ändern Sie das Verhalten des Steuerelements als Reaktion auf bestimmte Windows-Meldungen. Finden Sie unter [Zuordnen von Meldungen zu Funktionen](../mfc/reference/mapping-messages-to-functions.md).

1. Geben Sie die neuen Memberfunktionen, um die Funktionalität des Steuerelements (optional) erweitern.

Verwenden eines abgeleiteten Steuerelements in einem Dialogfeld ist zusätzliche Arbeit erforderlich. Die Typen und Positionen der Steuerelemente in einem Dialogfeld werden normalerweise in einer Dialogfeldvorlagen-Ressource angegeben. Wenn Sie eine Klasse abgeleitetes Steuerelement erstellen, können nicht Sie es in eine Dialogfeldvorlage angeben, da der Ressourcencompiler, nichts über die abgeleitete Klasse kennt.

#### <a name="to-place-your-derived-control-in-a-dialog-box"></a>Platzieren Sie das abgeleitete Steuerelement in einem Dialogfeld

1. Betten Sie ein Objekt der Klasse abgeleitete Steuerelement in der Deklaration der abgeleiteten Dialogfeldklasse.

1. Überschreiben der `OnInitDialog` Member-Funktion in Ihrer Dialogfeldklasse aufrufen, die `SubclassDlgItem` Member-Funktion für das abgeleitete Steuerelement.

`SubclassDlgItem` "dynamisch Unterklassen" erstellt ein Steuerelement aus einer Dialogfeldvorlage. Wenn ein Steuerelement dynamisch als Unterklasse definiert ist, Sie in Windows zu verknüpfen, einige Nachrichten innerhalb Ihrer eigenen Anwendung verarbeitet werden, und übergeben die verbleibenden Nachrichten an Windows. Weitere Informationen finden Sie unter den [SubclassDlgItem](../mfc/reference/cwnd-class.md#subclassdlgitem) Memberfunktion der Klasse `CWnd` in die *MFC-Referenz*. Das folgende Beispiel zeigt, wie Sie eine Überschreibung der schreiben `OnInitDialog` aufzurufende `SubclassDlgItem`:

[!code-cpp[NVC_MFCControlLadenDialog#3](../mfc/codesnippet/cpp/deriving-controls-from-a-standard-control_1.cpp)]

Da das abgeleitete Steuerelement in die Dialogfeldklasse eingebettet ist, wird er erstellt werden, wenn das Dialogfeld erstellt wird, und es werden zerstört, wenn das Dialogfeld zerstört wird. Vergleichen Sie diesen Code im Beispiel in [Hinzufügen von Steuerelementen By Hand](../mfc/adding-controls-by-hand.md).

## <a name="see-also"></a>Siehe auch

[Erstellen und Verwenden von Steuerelementen](../mfc/making-and-using-controls.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)
