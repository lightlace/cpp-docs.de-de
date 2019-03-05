---
title: Hinzufügen von Spalten zum Steuerelement (Berichtsansicht)
ms.date: 11/04/2016
helpviewer_keywords:
- CListCtrl class [MFC], adding columns
- report view in CListCtrl class [MFC]
- views [MFC], report
- columns [MFC], adding to CListCtrl
- CListCtrl class [MFC], report view
ms.assetid: 7392c0d7-f8a5-4e7b-9ae7-b53dc9dd80ae
ms.openlocfilehash: d414c5f597628576916c5091fa63a4bf673c8c44
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57292540"
---
# <a name="adding-columns-to-the-control-report-view"></a>Hinzufügen von Spalten zum Steuerelement (Berichtsansicht)

> [!NOTE]
>  Das folgende Verfahren gilt entweder eine [CListView](../mfc/reference/clistview-class.md) oder [CListCtrl](../mfc/reference/clistctrl-class.md) Objekt.

Wenn ein Listensteuerelement in der Berichtsansicht ist, werden Spalten angezeigt, die eine Methode zum Organisieren von verschiedenen Unterelemente für jedes Listenelement-Steuerelement. Dieser Organisation wird durch eine direkte Kommunikation zwischen einer Spalte im Steuerelement und dem Unterelement des Listenelements, an das Steuerelement implementiert. Weitere Informationen über Unterelemente finden Sie unter [Hinzufügen von Elementen zum Steuerelement](../mfc/adding-items-to-the-control.md). Ein Beispiel für ein Listensteuerelement, in der Berichtsansicht wird von der Ansicht in Windows 95 und Windows 98-Explorer bereitgestellt. Die erste Spalte listet die Ordner, Dateisymbole und Bezeichnungen. Andere Spalten enthalten die Dateigröße, Dateityp, Datum der letzten Änderung und So weiter.

Auch wenn die Spalten einem Listensteuerelement zu einem beliebigen Zeitpunkt hinzugefügt werden können, die Spalten sind sichtbar nur, wenn das Steuerelement enthält die `LVS_REPORT` Formatbit aktiviert.

Jede Spalte besitzt einen zugehörigen Headerelement (finden Sie unter [CHeaderCtrl](../mfc/reference/cheaderctrl-class.md)) Objekt, das die Spalte "Bezeichnungen" und ermöglicht es Benutzern, die Größe der Spalte ändern.

Wenn Ihr Listensteuerelement eine Berichtsansicht unterstützt, müssen Sie eine Spalte für jedes mögliche Unterelement in einem Steuerelement ein Element hinzuzufügen. Fügen Sie eine Spalte mit dem Vorbereiten einer [LV_COLUMN](/windows/desktop/api/commctrl/ns-commctrl-taglvcolumna) Struktur und durch einen Aufruf von [InsertColumn](../mfc/reference/clistctrl-class.md#insertcolumn). Nach dem Hinzufügen der erforderlichen Spalten (auch als Header-Elemente "bezeichnet), können neu angeordnet werden mithilfe von Memberfunktionen und Stile, die zu dem eingebetteten Kopfzeilen-Steuerelement gehören. Weitere Informationen finden Sie unter [Anordnen von Elementen im Headersteuerelement](../mfc/ordering-items-in-the-header-control.md).

> [!NOTE]
>  Wenn das Strukturelement-Steuerelement erstellt wird, mit der **LVS_NOCOLUMNHEADER** Stil, jeder Versuch, fügen Sie Spalten ignoriert werden.

## <a name="see-also"></a>Siehe auch

[Verwenden von CListCtrl](../mfc/using-clistctrl.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)
