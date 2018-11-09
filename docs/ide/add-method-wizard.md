---
title: Assistent zum Hinzufügen von Methoden
ms.date: 11/04/2016
f1_keywords:
- vc.codewiz.method.overview
helpviewer_keywords:
- Add Method Wizard [C++]
- methods [C++], adding using wizards
ms.assetid: b9a71b0e-9ecf-40fa-9f86-4200cb23d671
ms.openlocfilehash: e03f1fe925a82baa8c291ebf6fc6ccca34a00b90
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50547848"
---
# <a name="add-method-wizard"></a>Assistent zum Hinzufügen von Methoden

Verwenden Sie diesen Assistenten, um eine Methode zu einer Schnittstelle hinzuzufügen. Je nachdem, zu welchem Projekttyp oder Schnittstellentyp Sie eine Methode hinzufügen, zeigt der Assistent unterschiedliche Optionen an.

## <a name="names"></a>Namen

- **Rückgabetyp**

   Der von der Methode zurückgegebene Datentyp. `HRESULT` wird für alle Schnittstellentypen empfohlen, da dadurch ein gängiges Verfahren zum Zurückgeben von Fehlern bereitgestellt wird.

   |Schnittstellentyp|Beschreibung |
   |--------------------|-----------------|
   |Duale Schnittstelle|`HRESULT`. Kann nicht geändert werden.|
   |Benutzerdefinierte Schnittstelle|`HRESULT`. Kann nicht geändert werden.|
   |Lokale benutzerdefinierte Schnittstelle|Geben Sie einen eigenen Rückgabetyp an, oder wählen Sie einen aus der Liste aus.|
   |Disp-Schnittstelle|Geben Sie einen eigenen Rückgabetyp an, oder wählen Sie einen aus der Liste aus.|
   |Disp-Schnittstelle des MFC-ActiveX-Steuerelements|Wenn Sie eine vordefinierte Methode implementieren, wird der Rückgabetyp auf den entsprechenden Wert festgelegt und kann nicht geändert werden. Wenn Sie eine Methode aus der Liste **Methodenname** auswählen und auf **Benutzerdefiniert** klicken, wählen Sie unter **Methodentyp auswählen** einen Rückgabetyp aus der Liste aus.|

- **Methodenname**

   Legt den Namen für die Methode fest.

   |Schnittstellentyp|Beschreibung |
   |--------------------|-----------------|
   |Duale ATL-Schnittstelle, benutzerdefinierte Schnittstelle, lokale benutzerdefinierte Schnittstelle|Geben Sie einen eigenen Methodennamen an.|
   |MFC-Disp-Schnittstelle|Geben Sie einen eigenen Methodennamen an, oder wählen Sie einen vorgeschlagenen Methodennamen aus der Liste aus. Wenn Sie einen Namen aus der Liste auswählen, wird der entsprechende Wert im Feld **Rückgabetyp** angezeigt und kann nicht geändert werden.|
   |Disp-Schnittstelle des MFC-ActiveX-Steuerelements|Geben Sie eine eigene an, oder wählen Sie die vordefinierte Methode [DoClick](../mfc/reference/colecontrol-class.md#doclick) oder [Refresh](../mfc/reference/colecontrol-class.md#refresh) aus. Weitere Informationen finden Sie unter [MFC ActiveX Controls: Adding Stock Methods (MFC-ActiveX-Steuerelemente: Hinzufügen vordefinierter Methoden)](../mfc/mfc-activex-controls-adding-stock-methods.md).|

- **Methodentyp**

   Nur für MFC-ActiveX-Steuerelemente verfügbar. Wenn Sie einen Methodennamen im Feld **Methodenname** angeben, statt eine Methode aus der Liste auszuwählen, ist dieses Kontrollkästchen deaktiviert.

   Wenn Sie eine der Methoden aus der Liste **Methodenname** auswählen, wählen Sie die vordefinierte oder eine benutzerdefinierte Implementierung aus.

   |Methodentyp|Beschreibung |
   |-----------------|-----------------|
   |**Stock**|Der Standardwert. Fügt die vordefinierte Implementierung der Methode ein, die Sie aus der Liste **Methodenname** ausgewählt haben. **Rückgabetyp** kann nicht geändert werden, wenn Sie **Stock** (Vordefiniert) auswählen.|
   |**Benutzerdefiniert**|Fügt eine Stub-Implementierung der Methode ein, die Sie aus der Liste **Methodenname** ausgewählt haben. Für benutzerdefinierte Methodentypen können Sie einen eigenen Rückgabetyp angeben oder einen aus der Liste **Rückgabetyp** auswählen.|

- **Interner Name**

   Nur für benutzerdefinierte Methoden verfügbar, die zu einer MFC-Disp-Schnittstelle hinzugefügt wurden. Legt den Namen fest, der in der Dispatchzuordnung, der Headerdatei (.h) und in der Implementierungsdatei (.cpp) verwendet wird. Standardmäßig stimmt dieser Name mit dem **Methodennamen** überein. Sie können den Methodennamen ändern, wenn Sie mit einer MFC-Disp-Schnittstelle arbeiten, oder wenn Sie eine benutzerdefinierte Methode zur Disp-Schnittstelle eines MFC-ActiveX-Steuerelements hinzufügen.

   |Schnittstellentyp|Beschreibung |
   |--------------------|-----------------|
   |Duale ATL-Schnittstelle, benutzerdefinierte Schnittstelle, lokale benutzerdefinierte Schnittstelle|Nicht verfügbar|
   |MFC-Disp-Schnittstelle|Wird standardmäßig auf den Methodennamen festgelegt. Sie können den internen Namen bearbeiten.|
   |Disp-Schnittstelle des MFC-ActiveX-Steuerelements|Sie können den internen Namen nur für benutzerdefinierte Methoden festlegen. Vordefinierte Methoden verwenden keinen internen Namen.|

- **Parameterattribute**

   Legt zusätzliche Attribute für den Parameter fest, der unter **Parametername** festgelegt wurde.

   |Parameterattribut|Beschreibung |Zulässige Kombinationen|
   |-------------------------|-----------------|--------------------------|
   |**In**|Gibt an, dass der Parameter von der aufrufenden Prozedur an die aufgerufene Prozedur übergeben wird.|Nur **in**<br /><br /> **in** und **out**|
   |**Out**|Gibt an, dass der Zeigerparameter an von der aufgerufenen Prozedur an die aufrufende Prozedur zurückgegeben wird (vom Server an den Client).|Nur **out**<br /><br /> **in** und **out**<br /><br /> **out** und **retval**|
   |**retval**|Gibt an, dass der Parameter den Rückgabewert des Members empfängt.|**retval** und „out“|

- **Parametertyp**

   Legt den Datentyp des Parameters fest. Wählen Sie den Typ aus der Liste aus.

- **Parametername**

   Legt den Namen eines Parameters fest, der durch die Methode übergeben werden soll. Wenn Sie den Namen eingegeben haben, müssen Sie auf **Hinzufügen** klicken, um diesen zur Liste der Parameter hinzuzufügen, die durch die Methode übergeben werden. Wenn Sie keinen Parameternamen angeben, ignoriert der Assistent sämtliche ausgewählte Parameterattribute (nur ATL) oder **Parametertypen**.

   Wenn Sie auf **Hinzufügen** klicken, wird der Parametername in der **Parameterliste** angezeigt.

   > [!Note]
   > Wenn Sie einen Parameternamen angeben und dann auf **Fertig stellen** klicken, bevor Sie auf **Hinzufügen** klicken, wird der Parameter nicht zur Methode hinzugefügt. Sie müssen die Methode suchen und den Parameter manuell einfügen.

- **Add**

   Fügt den Parameter, seinen Typ und seine Parameterattribute der **Parameterliste** hinzu, den Sie in **Parametername** festlegen. Klicken Sie auf **Hinzufügen**, um einen Parameter zur Liste hinzuzufügen.

- **Entfernen**

   Entfernt den in der **Parameterliste** ausgewählten Parameter aus der Liste.

- **Parameterliste**

   Zeigt alle Parameter, die derzeit zur Methode hinzugefügt werden, sowie deren Modifizierer und Typen an. Während Sie Parameter hinzufügen, aktualisiert der Assistent die **Parameterliste**, um jeden Parameter einschließlich seiner Modifizierer und Typen anzuzeigen.

## <a name="see-also"></a>Siehe auch

[Hinzufügen einer Methode](../ide/adding-a-method-visual-cpp.md)<br/>
[IDL-Attribute, Assistent zum Hinzufügen von Methoden](../ide/idl-attributes-add-method-wizard.md)