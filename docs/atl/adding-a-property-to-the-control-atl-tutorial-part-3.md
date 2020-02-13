---
title: Hinzufügen einer Eigenschaft zum Steuerelement (ATL-Lernprogramm, Teil 3)
ms.custom: get-started-article
ms.date: 09/26/2018
ms.assetid: f775fe34-103b-4f07-9999-400e987ee030
ms.openlocfilehash: 288dc9f5af57c02639d15a9a971419a633cfc08d
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/11/2020
ms.locfileid: "77127586"
---
# <a name="adding-a-property-to-the-control-atl-tutorial-part-3"></a>Hinzufügen einer Eigenschaft zum Steuerelement (ATL-Lernprogramm, Teil 3)

`IPolyCtl` ist die Schnittstelle, die die benutzerdefinierten Methoden und Eigenschaften des Steuer Elements enthält, und Sie fügen ihr eine Eigenschaft hinzu.

### <a name="to-add-the-property-definitions-to-your-project"></a>So fügen Sie dem Projekt die Eigenschafts Definitionen hinzu

1. Erweitern Sie in **Klassenansicht**die `Polygon` Verzweigung.

1. Klicken Sie mit der rechten Maustaste `IPolyCtl`.

1. Klicken Sie im Kontextmenü auf **Hinzufügen**, und klicken Sie dann auf **Eigenschaft hinzufügen**. Der Assistent zum **Hinzufügen von Eigenschaften** wird angezeigt.

1. Geben Sie `Sides` als **Eigenschaftsnamen**ein.

1. Wählen Sie in der Dropdown Liste mit dem **Eigenschaftentyp**die Option `short`aus.

1. Klicken Sie auf **OK** , um die Eigenschaft hinzuzufügen.

1. Öffnen Sie in **Projektmappen-Explorer**Polygon. idl, und ersetzen Sie die folgenden Zeilen am Ende der `IPolyCtl : IDispatch` Schnittstelle:

    ```cpp
    short get_Sides();
    void set_Sides(short value);
    ```

    durch

    ```cpp
    [propget, id(1), helpstring("property Sides")] HRESULT Sides([out, retval] short *pVal);
    [propput, id(1), helpstring("property Sides")] HRESULT Sides([in] short newVal);
    ```

1. Öffnen Sie in **Projektmappen-Explorer**PolyCtl. h, und fügen Sie nach der Definition von `m_clrFillColor`die folgenden Zeilen hinzu:

    [!code-cpp[NVC_ATL_Windowing#44](../atl/codesnippet/cpp/adding-a-property-to-the-control-atl-tutorial-part-3_1.h)]

Obwohl Sie nun über Skelett Funktionen verfügen, um die Eigenschaft festzulegen und abzurufen, und eine Variable zum Speichern der Eigenschaft, müssen Sie die Funktionen entsprechend implementieren.

### <a name="to-update-the-get-and-put-methods"></a>So aktualisieren Sie die Get-und Put-Methoden

1. Legen Sie den Standardwert `m_nSides`fest. Legen Sie die Standardform zu einem Dreieck, indem Sie dem Konstruktor in PolyCtl. h eine Zeile hinzufügen:

    [!code-cpp[NVC_ATL_Windowing#45](../atl/codesnippet/cpp/adding-a-property-to-the-control-atl-tutorial-part-3_2.h)]

1. Implementieren Sie die Methoden `Get` und `Put`. Die `get_Sides`-und `put_Sides`-Funktions Deklarationen wurden PolyCtl. h hinzugefügt. Fügen Sie nun den Code für `get_Sides` und `put_Sides` zu "PolyCtl. cpp" hinzu:

    [!code-cpp[NVC_ATL_Windowing#46](../atl/codesnippet/cpp/adding-a-property-to-the-control-atl-tutorial-part-3_3.cpp)]

Die `get_Sides`-Methode gibt den aktuellen Wert der Eigenschaft `Sides` über den `pVal`-Zeiger zurück. In der `put_Sides`-Methode stellt der Code sicher, dass der Benutzer die `Sides`-Eigenschaft auf einen zulässigen Wert festlegt. Der Minimalwert muss 3 sein, und da ein Array von Punkten für jede Seite verwendet wird, ist 100 eine angemessene Grenze für einen maximalen Wert.

Sie verfügen nun über eine Eigenschaft mit dem Namen `Sides`. Im nächsten Schritt ändern Sie den Zeichnungs Code, um ihn zu verwenden.

[Zurück zu Schritt 2](../atl/adding-a-control-atl-tutorial-part-2.md) &#124; für [Schritt 4](../atl/changing-the-drawing-code-atl-tutorial-part-4.md)

## <a name="see-also"></a>Weitere Informationen

[Tutorial](../atl/active-template-library-atl-tutorial.md)
