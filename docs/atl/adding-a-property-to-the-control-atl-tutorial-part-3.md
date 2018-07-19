---
title: Hinzufügen einer Eigenschaft zum Steuerelement (ATL-Lernprogramm, Teil 3) | Microsoft-Dokumentation
ms.custom: get-started-article
ms.date: 11/04/2016
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
ms.openlocfilehash: 7cbfb0b22579aceb5cbee196e3c5eda3079c9304
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/05/2018
ms.locfileid: "37848716"
---
# <a name="adding-a-property-to-the-control-atl-tutorial-part-3"></a>Hinzufügen einer Eigenschaft zum Steuerelement (ATL-Lernprogramm, Teil 3)
`IPolyCtl` ist die Schnittstelle, die das Steuerelement die benutzerdefinierten Methoden und Eigenschaften enthält, und fügen Sie eine Eigenschaft zuzuweisen.  
  
### <a name="to-add-a-property-using-the-add-property-wizard"></a>Zum Hinzufügen einer Eigenschaft mithilfe des Assistenten zum Hinzufügen von Eigenschaften  
  
1.  Erweitern Sie in der Klassenansicht den Polygon-Branch aus.  
  
2.  Mit der rechten Maustaste IPolyCtl.  
  
3.  Klicken Sie im Kontextmenü auf **hinzufügen**, und klicken Sie dann auf **Eigenschaft hinzufügen**.  
  
     Der Assistent zum Hinzufügen von Eigenschaften wird angezeigt.  
  
4.  Wählen Sie in der Dropdown-Liste von Eigenschaftentypen `SHORT`.  
  
5.  Typ *Seiten* als die **Eigenschaftenname.**  
  
6.  Klicken Sie auf **Fertig stellen** auf die Eigenschaft hinzuzufügen.  
  
 MIDL (das Programm, die IDL-Dateien kompiliert) wird definiert, wenn Sie die Eigenschaft auf die Schnittstelle hinzufügen, eine `Get` Methode zum Abrufen des Wertes und `Put` -Methode für einen neuen Wert festlegen. Die Methoden werden mit dem Namen vorangestellt `put_` und `get_` an den Eigenschaftennamen an.  
  
 Der Assistent zum Hinzufügen von Eigenschaften fügt die erforderlichen Zeilen der IDL-Datei. Sie fügt außerdem die `Get` und `Put` Funktionsprototypen der Klassendefinition in PolyCtl.h hinzu und fügt eine leere Implementierung PolyCtl.cpp. Sie können dies überprüfen, indem Sie die PolyCtl.cpp öffnen, und suchen Sie für die Funktionen `get_Sides` und `put_Sides`.  
  
 Obwohl Sie Gerüstfunktionen festlegen und Abrufen der Eigenschaft jetzt verfügen, benötigt es einen Ort gespeichert werden. Erstellen Sie eine Variable zum Speichern der Eigenschaft, die Funktionen entsprechend aktualisieren.  
  
#### <a name="to-create-a-variable-to-store-the-property-and-update-the-put-and-get-methods"></a>Erstellen Sie eine Variable zum Speichern der Eigenschaft, und aktualisieren die Put, get-Methoden  
  
1.  Öffnen Sie im Projektmappen-Explorer PolyCtl.h hinzu, und fügen Sie die folgende Zeile nach der Definition der `m_clrFillColor`:  
  
     [!code-cpp[NVC_ATL_Windowing#44](../atl/codesnippet/cpp/adding-a-property-to-the-control-atl-tutorial-part-3_1.h)]  
  
2.  Legen Sie den Standardwert `m_nSides`. Stellen Sie die Standardeinstellung, die ein Dreieck Form durch Hinzufügen einer Zeile an den Konstruktor in PolyCtl.h hinzu:  
  
     [!code-cpp[NVC_ATL_Windowing#45](../atl/codesnippet/cpp/adding-a-property-to-the-control-atl-tutorial-part-3_2.h)]  
  
3.  Implementieren der `Get` und `Put` Methoden. Die `get_Sides` und `put_Sides` Funktionsdeklarationen PolyCtl.h hinzugefügt wurden. Ersetzen Sie den Code in PolyCtl.cpp für `get_Sides` und `put_Sides` durch den folgenden Code:  
  
     [!code-cpp[NVC_ATL_Windowing#46](../atl/codesnippet/cpp/adding-a-property-to-the-control-atl-tutorial-part-3_3.cpp)]  
  
 Die `get_Sides` Methode gibt den aktuellen Wert des der `Sides` Eigenschaft über die `pVal` Zeiger. In der `put_Sides` -Methode, die der Code stellt sicher ist der Benutzer das Festlegen der `Sides` Eigenschaft einen zulässigen Wert. Der Minimalwert muss 3 sein, und da ein Array von Punkten für jede Seite verwendet wird, handelt es sich bei 100 ist ein vernünftiges Maß beschränken für einen maximalen Wert.  
  
 Sie verfügen nun über eine Eigenschaft namens `Sides`. Im nächsten Schritt ändern Sie den Code für dessen Verwendung zum Zeichnen.  
  
 [Zurück zu Schritt 2.](../atl/adding-a-control-atl-tutorial-part-2.md) &#124; [mit Schritt 4](../atl/changing-the-drawing-code-atl-tutorial-part-4.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Tutorial](../atl/active-template-library-atl-tutorial.md)

