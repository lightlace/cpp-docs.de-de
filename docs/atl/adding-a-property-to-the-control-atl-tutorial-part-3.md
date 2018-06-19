---
title: Hinzufügen einer Eigenschaft zum Steuerelement (ATL-Lernprogramm, Teil 3) | Microsoft Docs
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
ms.openlocfilehash: fda9359da6ddc48248874227d58f0c184af45c54
ms.sourcegitcommit: 9b442b44ee912822d06cabec826aac4a8d82ec75
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/24/2018
ms.locfileid: "34472085"
---
# <a name="adding-a-property-to-the-control-atl-tutorial-part-3"></a>Hinzufügen einer Eigenschaft zum Steuerelement (ATL-Lernprogramm, Teil 3)
`IPolyCtl` ist die Schnittstelle, die das Steuerelement benutzerdefinierte Methoden und Eigenschaften enthält, und fügen Sie eine Eigenschaft zu.  
  
### <a name="to-add-a-property-using-the-add-property-wizard"></a>So fügen Sie einer Eigenschaft mithilfe des Assistenten zum Hinzufügen von Eigenschaften hinzu  
  
1.  Erweitern Sie in der Klassenansicht das Polygon-Verzweigung aus.  
  
2.  Mit der rechten Maustaste IPolyCtl.  
  
3.  Klicken Sie im Kontextmenü auf **hinzufügen**, und klicken Sie dann auf **Eigenschaft hinzufügen**.  
  
     Der Assistent zum Hinzufügen von Eigenschaften wird angezeigt.  
  
4.  Wählen Sie in der Dropdown-Liste von Eigenschaftentypen `SHORT`.  
  
5.  Typ `Sides` als die **Eigenschaftsname.**  
  
6.  Klicken Sie auf **Fertig stellen** auf die Eigenschaft hinzuzufügen.  
  
 Wenn Sie die Eigenschaft auf die Schnittstelle hinzufügen, MIDL (das Programm, das kompiliert IDL-Dateien) definiert ein `Get` Methode zum Abrufen des Wertes und eine `Put` Methode zum Festlegen eines neuen Werts. Die Methoden werden mit dem Namen vorangestellt `put_` und `get_` des Eigenschaftennamens.  
  
 Der Assistent zum Hinzufügen von Eigenschaften hinzugefügt der IDL-Datei die erforderlichen Zeilen. Sie fügt außerdem die `Get` und `Put` memberfunktionsprototypen der Klassendefinition in PolyCtl.h hinzu und fügt eine leere Implementierung PolyCtl.cpp. Sie können überprüfen, indem PolyCtl.cpp öffnen und den Funktionen wünschen `get_Sides` und `put_Sides`.  
  
 Obwohl Sie nun das Gerüst eines Funktionen festlegen und Abrufen der Eigenschaft, benötigt er einen Ort gespeichert werden soll. Erstellen Sie eine Variable, um die Eigenschaft zu speichern und aktualisieren Sie dementsprechend die Funktionen.  
  
#### <a name="to-create-a-variable-to-store-the-property-and-update-the-put-and-get-methods"></a>So erstellen eine Variable, um die Eigenschaft, speichern und Aktualisieren der Put und get-Methoden  
  
1.  Öffnen Sie im Projektmappen-Explorer PolyCtl.h hinzu, und fügen Sie die folgende Zeile nach der Definition von `m_clrFillColor`:  
  
     [!code-cpp[NVC_ATL_Windowing#44](../atl/codesnippet/cpp/adding-a-property-to-the-control-atl-tutorial-part-3_1.h)]  
  
2.  Legen Sie den Standardwert `m_nSides`. Stellen Sie die Standardeinstellung, ein Dreieck Form durch Hinzufügen einer Zeile an den Konstruktor in PolyCtl.h hinzu:  
  
     [!code-cpp[NVC_ATL_Windowing#45](../atl/codesnippet/cpp/adding-a-property-to-the-control-atl-tutorial-part-3_2.h)]  
  
3.  Implementieren der `Get` und `Put` Methoden. Die `get_Sides` und `put_Sides` Funktionsdeklarationen PolyCtl.h hinzugefügt wurden. Ersetzen Sie den Code in PolyCtl.cpp für `get_Sides` und `put_Sides` durch den folgenden Code:  
  
     [!code-cpp[NVC_ATL_Windowing#46](../atl/codesnippet/cpp/adding-a-property-to-the-control-atl-tutorial-part-3_3.cpp)]  
  
 Die `get_Sides` Methode gibt den aktuellen Wert von der `Sides` Eigenschaft über die `pVal` Zeiger. In der `put_Sides` -Methode, der Code wird sichergestellt, dass der Benutzer wird das Festlegen der `Sides` Eigenschaft auf einen akzeptablen Wert. Der Minimalwert muss 3 sein, und da ein Array von Punkten für jede Seite verwendet werden, ist 100 für einen Höchstwert ein vernünftiges Maß beschränken.  
  
 Sie verfügen nun über eine Eigenschaft mit dem Namen `Sides`. Im nächsten Schritt ändern Sie den Code für dessen Verwendung zum Zeichnen.  
  
 [Zurück zu Schritt 2](../atl/adding-a-control-atl-tutorial-part-2.md) &#124; [mit Schritt 4 fort](../atl/changing-the-drawing-code-atl-tutorial-part-4.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Lernprogramm](../atl/active-template-library-atl-tutorial.md)

