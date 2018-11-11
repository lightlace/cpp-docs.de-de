---
title: Namen, Assistent zum Hinzufügen von Eigenschaften
ms.date: 11/04/2016
f1_keywords:
- vc.codewiz.prop.overview
ms.assetid: 0453b7ea-89cb-41a1-80a2-d45f61589c0a
ms.openlocfilehash: 1cb37b2e8f3efd9ff9789a315e6bf32add730708
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50636916"
---
# <a name="names-add-property-wizard"></a>Namen, Assistent zum Hinzufügen von Eigenschaften

Verwenden Sie diesen Assistenten, um eine Eigenschaft zu einer Schnittstelle hinzuzufügen.

- **Eigenschaftentyp**

   Legt den Typ der Eigenschaft fest, die Sie hinzufügen. Geben Sie bei MFC-Disp-Schnittstellen einen eigenen Typ an, oder wählen Sie einen aus der vordefinierten Liste aus. Wenn Sie eine vordefinierte Implementierung einer Eigenschaft bereitstellen, wird **Eigenschaftentyp** auf den vordefinierten Typ festgelegt und kann nicht geändert werden.

- **Eigenschaftenname**

   Legt den Namen der Eigenschaft fest. Für MFC-Disp-Schnittstellen, die ActiveX-Steuerelementen zugeordnet sind, können Sie einen eigenen Namen angeben oder einen vordefinierten Eigenschaftennamen aus der Liste auswählen. Wenn Sie einen eigenen Eigenschaftennamen bereitstellen, ist der Implementierungstyp **Stock** (Vordefiniert) nicht verfügbar. Eine Beschreibung der Eigenschaften in der Liste finden Sie unter [Basiseigenschaften](../ide/stock-properties.md).

   |Schnittstellentyp|Beschreibung |
   |--------------------|-----------------|
   |Duale ATL-Schnittstelle, benutzerdefinierte Schnittstelle, lokale benutzerdefinierte Schnittstelle|Geben Sie einen Eigenschaftennamen an.|
   |MFC-Disp-Schnittstelle, Disp-Schnittstelle des MFC-ActiveX-Steuerelements|Geben Sie einen Eigenschaftennamen an, oder wählen Sie eine Basiseigenschaft aus der Liste aus. Wenn Sie eine Eigenschaft aus der Liste auswählen, wird der entsprechende Wert im Feld **Eigenschaftentyp** angezeigt. Sie können diesen Typ abhängig von Ihrer Auswahl unter **Implementierungstyp** ändern.|

- **Rückgabetyp**

   Nur ATL-Schnittstellen Legt den Rückgabetyp der Eigenschaft fest. Bei dualen Schnittstellen ist der Rückgabetyp immer `HRESULT`, und das Feld ist nicht verfügbar. Bei benutzerdefinierten Schnittstellen können Sie einen Rückgabetyp aus der Liste auswählen. `HRESULT` wird dennoch empfohlen, da dadurch ein gängiges Verfahren zum Zurückgeben von Fehlern bereitgestellt wird.

- **Variablenname**

   Nur MFC-Schnittstellen Nur verfügbar, wenn Sie **Membervariable** unter **Implementierungstyp** festlegen. Legt den Namen der Membervariable fest, der die Eigenschaft zugeordnet ist. Der Variablenname ist standardmäßig auf „m_*PropertyName*“ festgelegt. Sie können diesen Namen bearbeiten.

- **Benachrichtigungsfunktion**

   Nur MFC-Schnittstellen Nur verfügbar, wenn Sie **Membervariable** unter **Implementierungstyp** festlegen. Legt den Namen der Benachrichtigungsfunktion fest, die aufgerufen wird, wenn die Eigenschaft geändert wird. Standardmäßig ist der Name der Benachrichtigungsfunktion auf „On*PropertyName*Changed“ festgelegt. Sie können diesen Namen bearbeiten.

- **Get-Funktion**

   Nur MFC-Disp-Schnittstellen Nur verfügbar, wenn Sie **Get/Set-Methoden** unter **Implementierungstyp** festlegen. Legt den Namen der Funktion fest, die die Eigenschaft abrufen soll. Standardmäßig ist der Name der Get-Funktion auf „Get*PropertyName*“ festgelegt. Sie können diesen Namen bearbeiten. Wenn Sie den Namen löschen, wird die Funktion [GetNotSupported](../mfc/reference/colecontrol-class.md#getnotsupported) in die Dispatchzuordnung der Schnittstelle eingefügt. Die Funktion „Get*PropertyName*“ gibt an, dass die Eigenschaft lesbar ist.

- **Funktion festlegen**

   Nur MFC-Schnittstellen Nur verfügbar, wenn Sie **Get/Set-Methoden** unter **Implementierungstyp** festlegen. Legt den Namen der Funktion fest, die die Eigenschaft festlegen soll. Standardmäßig ist der Name der Set-Funktion auf „Set*PropertyName*“ festgelegt. Sie können diesen Namen bearbeiten. Wenn Sie den Namen löschen, wird die Funktion [SetNotSupported](../mfc/reference/colecontrol-class.md#setnotsupported) in die Dispatchzuordnung der Schnittstelle eingefügt. Die Funktion „Set*PropertyName*“ gibt an, dass die Eigenschaft schreibbar ist.

- **Implementierungstyp**

   Nur MFC-Schnittstellen Gibt an, wie die hinzugefügten Eigenschaften implementiert werden sollen.

   |Implementierungstyp|Beschreibung |
   |-------------------------|-----------------|
   |**Stock**|Gibt eine vordefinierte Implementierung für die unter **Eigenschaftenname** ausgewählte Eigenschaft an. Der Standardwert. Weitere Informationen finden Sie unter [Basiseigenschaften](../ide/stock-properties.md).<br /><br /> Wenn Sie **Stock** (Vordefiniert) angeben, werden **Eigenschaftentyp**, **Parametertyp** und **Parametername** abgeblendet.|
   |**Membervariable**|Gibt an, dass die Eigenschaft als Membervariable hinzugefügt wird. Sie können benutzerdefinierte Eigenschaften und die meisten Basiseigenschaften als Membervariablen hinzufügen. Sie können **Beschriftungs-**, **hWnd-** und **Texteigenschaften** nicht als **Membervariable** festlegen.<br /><br /> Gibt Standardnamen unter **Variablenname** und **Benachrichtigungsfunktion** an. Sie können diesen Namen bearbeiten.|
   |**Get/Set-Methoden**|Gibt an, dass die Eigenschaft standardmäßig als Get*PropertyName*- und Set*PropertyName*-Funktion hinzugefügt wird. Diese Namen werden unter **Get-Funktion** und **Set-Funktion** angezeigt.<br /><br /> Sie können den standardmäßig festgelegten **Eigenschaftentyp** ändern, wodurch ein Wert an die Get-Funktion übergeben wird. Sie können Parameter für die **Get**- und `Set`-Funktionen angeben.|

- **Get-Funktion**

   ATL-Schnittstellen Legt diese Eigenschaft als lesbar fest. Die **Get**-Methode wird also erstellt, um diese Eigenschaft aus dem Objekt abzurufen. Sie müssen **Get**, `Put` oder beides auswählen.

- **Put-Funktion**

   Nur ATL-Schnittstellen Legt die Eigenschaft als schreibbar fest. Die `Put`-Methode wird also für das Festlegen bzw. „Einfügen“ dieser Eigenschaft des Objekts erstellt. Sie müssen **Get**, `Put` oder beides auswählen. Wenn Sie diese Option auswählen, können Sie die Methode auf zwei Arten implementieren:

   |Option|Beschreibung |
   |------------|-----------------|
   |**PropPut**|Die [PropPut](../windows/propput.md)-Funktion gibt eine Kopie des Objekts zurück. Dies ist die Standardeinstellung und die gängigste Methode, um die Eigenschaft schreibbar zu machen.|
   |**PropPutRef**|Die [PropPutRef](../windows/propputref.md)-Funktion gibt einen Verweis auf das Objekt statt einer Kopie des Objekts zurück. Diese Option sollten Sie für Objekte (z.B. große Strukturen oder Arrays) verwenden, deren Initialisierung aufwändig sein kann.|

- **Parameterattribute**

   Nur ATL-Schnittstellen Legt fest, ob der Parameter, der durch **Parametername** festgelegt wurde, **in**, **out**, beides oder keines davon ist.

   |Option|Beschreibung |
   |------------|-----------------|
   |**in**|Gibt an, dass der Parameter von der aufrufenden Prozedur an die aufgerufene Prozedur übergeben wird.|
   |**out**|Gibt an, dass der Zeigerparameter an von der aufgerufenen Prozedur an die aufrufende Prozedur zurückgegeben wird (vom Server an den Client).|

- **Parametertyp**

   Legt den Datentyp des Parameters fest. Wählen Sie den Typ aus der Liste aus.

- **Parametername**

   Legt den Namen eines Parameters fest, den Sie zur Eigenschaft hinzufügen, sofern die Eigenschaft über Parameter verfügt. Wenn Sie auf **Hinzufügen** klicken, wird der Parametername in der **Parameterliste** angezeigt.

- **Parameterliste**

   Zeigt die Liste der Attribute an, die zur Eigenschaft hinzugefügt werden sollen. Jedes Element in der Liste besteht aus dem Parameternamen, dem Parametertyp und den Attributen. Verwenden Sie **Hinzufügen** und **Entfernen**, um die Liste zu aktualisieren.

- **Add**

   Fügt den Parameter hinzu, den Sie in **Parametername** und **Parametertyp** eingeben, zur **Parameterliste** hinzu. Klicken Sie auf **Hinzufügen**, um einen Parameter zur Liste hinzuzufügen.

- **Entfernen**

   Entfernt den ausgewählten Parameter aus der **Parameterliste**.

- **Standardeigenschaft**

   Nur MFC-Disp-Schnittstellen Legt diese Eigenschaft als Standard für die Schnittstelle fest. Eine Schnittstelle kann nur eine Standardeigenschaft besitzen. Sobald Sie die Standardeigenschaft angeben, ist dieses Feld für jede weitere Eigenschaft, die Sie zur Schnittstelle hinzufügen, nicht verfügbar.

## <a name="see-also"></a>Siehe auch

[Hinzufügen einer Eigenschaft](../ide/adding-a-property-visual-cpp.md)<br>
[IDL-Attribute, Assistent zum Hinzufügen von Eigenschaften](../ide/idl-attributes-add-property-wizard.md)<br>
[Implementieren einer Schnittstelle](../ide/implementing-an-interface-visual-cpp.md)