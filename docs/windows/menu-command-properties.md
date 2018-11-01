---
title: Menübefehlseigenschaften (C++)
ms.date: 11/04/2016
helpviewer_keywords:
- menu items, properties
ms.assetid: 6d308205-3c9e-42f2-ab42-45e656940e45
ms.openlocfilehash: ddb33293d654944aa9390b9955388d6e3b01cddb
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50468977"
---
# <a name="menu-command-properties-c"></a>Menübefehlseigenschaften (C++)

Die folgenden Informationen sind entsprechend so aufgebaut, dass die **Menü** Eigenschaften, die in der [Fenster "Eigenschaften"](/visualstudio/ide/reference/properties-window) bei der Auswahl eines Menübefehls. Diese sind alphabetisch aufgeführt, obwohl die **Eigenschaften** Fenster auch können Sie diese Eigenschaften nach Kategorie anzuzeigen.

|Eigenschaft|Beschreibung|
|--------------|-----------------|
|**Break**|Einer der folgenden Werte ist möglich:<br /><br />- **Kein** (Standard): Kein Wechsel.<br />- **Spalte**: Bei statischen Menüs bewirkt dieser Wert, dass der Menübefehl in eine neue Zeile gesetzt wird. Bei Popupmenüs bewirkt dieser Wert, dass der Menübefehl in eine neue Spalte gesetzt wird, ohne dass zwischen den Spalten eine Trennlinie angezeigt wird. Diese Eigenschaft wirkt sich nicht im Menü-Editor, sondern erst zur Laufzeit auf die Darstellung des Menüs aus.<br />- **Leiste**: identisch mit **Spalte** außer dass bei Popupmenüs dieser Wert die neue Spalte von der alten Spalte getrennt durch eine vertikale Linie. Diese Eigenschaft wirkt sich auf die Darstellung des Menüs nur zur Laufzeit nicht in der **Menü** Editor.|
|**Beschriftung**|Text zur Beschreibung des Menübefehls (der Menüname). Einem der Buchstaben in der Beschriftung eines Menübefehls kann eine Zugriffstaste zugeordnet werden, indem ihm ein kaufmännisches Und-Zeichen (&) vorangestellt wird.|
|**Aktiviert**|Wenn **"true"**, der Menübefehl zu Beginn aktiviert ist. Typ: **"bool"**. Standardwert: **FALSE**.|
|**Aktiviert**|Wenn **FALSE**, ist das Menüelement deaktiviert.|
|**Grau**|Wenn **"true"**, ist der Menübefehl, Beginn grau dargestellt und inaktiv. Typ: **"bool"**. Standardwert: **FALSE**.|
|**Hilfe**|Richtet das Menüelement rechtsbündig aus. Der Menübefehl für die **Hilfe** befindet sich beispielsweise in allen Windows-Anwendungen immer ganz rechts. Wenn Sie diese Eigenschaft für ein Menüelement festlegen, wird das Element ganz rechts am Ende des Menüs angezeigt. Bezieht sich auf Elemente des Hauptmenüs. Standardwert: **FALSE**.|
|**ID**|Ein Symbol, das in der Headerdatei definiert ist. Typ: **Symbol**, **Ganzzahl**, oder **Zeichenfolge in Anführungszeichen**. Sie können ein beliebiges Symbol verwenden, das üblicherweise in den Editoren verfügbar ist. Dies gilt auch, wenn das [Eigenschaftenfenster](/visualstudio/ide/reference/properties-window) keine Dropdownliste enthält, aus der Sie auswählen können.|
|**Popup**|Wenn **"true"**, der Menübefehl ist ein Popup-Menü. Typ: **"bool"**. Standardwert: **"true"** für Menüs der obersten Ebene in einer Menüleiste; andernfalls **"false"**.|
|**Eingabeaufforderung**|Enthält Text, der in der Statusleiste angezeigt werden soll, wenn dieser Menübefehl markiert wird. Der Text wird mit dem Bezeichner des Menübefehls in der Zeichenfolgentabelle gespeichert. Diese Eigenschaft ist für jeden Projekttyp verfügbar, wobei die Laufzeitfunktionalität jedoch MFC-spezifisch ist.|
|**Rechtsbündig**|Richtet den Menübefehl auf der Menüleiste zur Laufzeit rechtsbündig aus. Typ: **"bool"**. Standardwert: **FALSE**.|
|**Von rechts nach links**|Ermöglicht die Darstellung der Menübefehle von rechts nach links, wenn die Benutzeroberfläche in eine Sprache übertragen werden soll, die von rechts nach links geschrieben wird, z. B. Hebräisch oder Arabisch.|
|**Trennzeichen**|Wenn **"true"**, der Menübefehl ein Trennzeichen ist. Typ: **"bool"**. Standardwert: **FALSE**.|

## <a name="requirements"></a>Anforderungen

Win32

## <a name="see-also"></a>Siehe auch

[Menü-Editor](../windows/menu-editor.md)