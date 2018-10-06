---
title: Hinzufügen einer Eigenschaft zum Steuerelement (ATL-Lernprogramm, Teil 3) | Microsoft-Dokumentation
ms.custom: get-started-article
ms.date: 09/26/2018
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: f775fe34-103b-4f07-9999-400e987ee030
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2373d2d703f18824274df158b31023669d8df945
ms.sourcegitcommit: a738519aa491a493a8f213971354356c0e6a5f3a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/05/2018
ms.locfileid: "48820467"
---
# <a name="adding-a-property-to-the-control-atl-tutorial-part-3"></a>Hinzufügen einer Eigenschaft zum Steuerelement (ATL-Lernprogramm, Teil 3)

`IPolyCtl` ist die Schnittstelle, die das Steuerelement die benutzerdefinierten Methoden und Eigenschaften enthält, und fügen Sie eine Eigenschaft zuzuweisen.

### <a name="to-add-the-property-definitions-to-your-project"></a>Die Eigenschaftendefinitionen zu Ihrem Projekt hinzufügen

1. In **Klassenansicht**, erweitern Sie die `Polygon` Branch.

1. Mit der rechten Maustaste `IPolyCtl`.

1. Klicken Sie im Kontextmenü auf **hinzufügen**, und klicken Sie dann auf **Eigenschaft hinzufügen**. Die **Eigenschaft hinzufügen** -Assistent wird angezeigt.

1. Typ `Sides` als die **Eigenschaftennamen**.

1. In der Dropdown-Liste der **Eigenschaftentyp**Option `short`.

1. Klicken Sie auf **OK** auf die Eigenschaft hinzuzufügen.

1. Von **Projektmappen-Explorer**Polygon.idl öffnen, und Ersetzen Sie die folgenden Zeilen am Ende der `IPolyCtl : IDispatch` Schnittstelle:

    ```cpp
    short get_Sides();
    void set_Sides(short value);
    ```

    durch

    ```cpp
    [propget, id(1), helpstring("property Sides")] HRESULT Sides([out, retval] short *pVal);
    [propput, id(1), helpstring("property Sides")] HRESULT Sides([in] short newVal);
    ```

1. Von **Projektmappen-Explorer**, öffnen Sie PolyCtl.h hinzu, und fügen Sie die folgenden Zeilen nach der Definition der `m_clrFillColor`:

    [!code-cpp[NVC_ATL_Windowing#44](../atl/codesnippet/cpp/adding-a-property-to-the-control-atl-tutorial-part-3_1.h)]

Obwohl Sie Gerüstfunktionen zum Festlegen und Abrufen der Eigenschaft und eine Variable zum Speichern der Eigenschaft jetzt haben, müssen Sie entsprechend die Funktionen implementieren.

### <a name="to-update-the-get-and-put-methods"></a>Aktualisieren die Get und put-Methoden

1. Legen Sie den Standardwert `m_nSides`. Stellen Sie die Standardeinstellung, die ein Dreieck Form durch Hinzufügen einer Zeile an den Konstruktor in PolyCtl.h hinzu:

    [!code-cpp[NVC_ATL_Windowing#45](../atl/codesnippet/cpp/adding-a-property-to-the-control-atl-tutorial-part-3_2.h)]

1. Implementieren der `Get` und `Put` Methoden. Die `get_Sides` und `put_Sides` Funktionsdeklarationen PolyCtl.h hinzugefügt wurden. Fügen Sie nun den Code für `get_Sides` und `put_Sides` PolyCtl.cpp durch Folgendes:

    [!code-cpp[NVC_ATL_Windowing#46](../atl/codesnippet/cpp/adding-a-property-to-the-control-atl-tutorial-part-3_3.cpp)]

Die `get_Sides` Methode gibt den aktuellen Wert des der `Sides` Eigenschaft über die `pVal` Zeiger. In der `put_Sides` -Methode, die der Code stellt sicher ist der Benutzer das Festlegen der `Sides` Eigenschaft einen zulässigen Wert. Der Minimalwert muss 3 sein, und da ein Array von Punkten für jede Seite verwendet wird, handelt es sich bei 100 ist ein vernünftiges Maß beschränken für einen maximalen Wert.

Sie verfügen nun über eine Eigenschaft namens `Sides`. Im nächsten Schritt ändern Sie den Code für dessen Verwendung zum Zeichnen.

[Zurück zu Schritt 2.](../atl/adding-a-control-atl-tutorial-part-2.md) &#124; [mit Schritt 4](../atl/changing-the-drawing-code-atl-tutorial-part-4.md)

## <a name="see-also"></a>Siehe auch

[Tutorial](../atl/active-template-library-atl-tutorial.md)
