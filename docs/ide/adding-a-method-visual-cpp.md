---
title: Hinzufügen einer Methode
ms.date: 11/09/2018
f1_keywords:
- vc.codewiz.method.overview
- vc.codewiz.method.idlattrib
helpviewer_keywords:
- add method wizard [C++]
- methods [C++], adding
- methods [C++], adding using wizards
- IDL attributes, add method wizard
ms.assetid: 4ba4e45f-fa38-4d5e-af44-cbec0a7ab558
ms.openlocfilehash: 23fb05e633713016b1f6289f73a916502736af10
ms.sourcegitcommit: b032daf81cb5fdb1f5a988277ee30201441c4945
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/15/2018
ms.locfileid: "51692684"
---
# <a name="add-a-method"></a>Hinzufügen einer Methode

Sie können den [Assistenten zum Hinzufügen von Methoden](#add-method-wizard) verwenden, um einer Schnittstelle in Ihrem Projekt eine Methode hinzuzufügen. Wenn das Projekt eine Klasse enthält, die der Schnittstelle zugeordnet ist, ändert der Assistent auch die Klasse.

**So fügen Sie Ihrem Projekt eine Methode hinzu:**

1. Erweitern Sie den Projektknoten in der **Klassenansicht**, um die Schnittstelle anzuzeigen, der die Methode hinzugefügt werden soll.

   > [!NOTE]
   > Sie können Methoden auch zu Disp-Schnittstellen hinzufügen, die sich unter dem Bibliotheksknoten befinden, sofern das Projekt nicht attributiert ist.

1. Klicken Sie mit der rechten Maustaste auf den Namen der Schnittstelle.

1. Wählen Sie im Kontextmenü **Hinzufügen** und dann **Methode hinzufügen** aus.

1. Geben Sie im Assistenten zum Hinzufügen von Methoden die Informationen zum Erstellen der Methode an.

1. Geben Sie alle Einstellungen der Interface Definiton Language dieser Methode auf der Seite [IDL-Attribute](#idl-attributes-add-method-wizard) des Assistenten an.

1. Klicken Sie auf **Fertig stellen**, um die Methode hinzuzufügen.

## <a name="in-this-section"></a>In diesem Abschnitt

- [Assistent zum Hinzufügen von Methoden](#add-method-wizard)
- [IDL-Attribute, Assistent zum Hinzufügen von Methoden](#idl-attributes-add-method-wizard)

## <a name="add-method-wizard"></a>Assistent zum Hinzufügen von Methoden

Verwenden Sie diesen Assistenten, um eine Methode zu einer Schnittstelle hinzuzufügen. Je nachdem, zu welchem Projekttyp oder Schnittstellentyp Sie eine Methode hinzufügen, zeigt der Assistent unterschiedliche Optionen an.

### <a name="names"></a>Namen

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
  |Duale ATL-Schnittstelle, benutzerdefinierte Schnittstelle, lokale benutzerdefinierte Schnittstelle|Nicht verfügbar.|
  |MFC-Disp-Schnittstelle|Wird standardmäßig auf den Methodennamen festgelegt. Sie können den internen Namen bearbeiten.|
  |Disp-Schnittstelle des MFC-ActiveX-Steuerelements|Sie können den internen Namen nur für benutzerdefinierte Methoden festlegen. Vordefinierte Methoden verwenden keinen internen Namen.|

- **Parameterattribute**

  Legt zusätzliche Attribute für den Parameter fest, der unter **Parametername** festgelegt wurde.

  |Parameterattribut|Beschreibung |Zulässige Kombinationen|
  |-------------------------|-----------------|--------------------------|
  |**In**|Gibt an, dass der Parameter von der aufrufenden Prozedur an die aufgerufene Prozedur übergeben wird.|Nur `in`<br /><br /> `in` und `out`|
  |**Out**|Gibt an, dass der Zeigerparameter an von der aufgerufenen Prozedur an die aufrufende Prozedur zurückgegeben wird (vom Server an den Client).|Nur `out`<br /><br /> `in` und `out`<br /><br /> `out` und `retval`|
  |**retval**|Gibt an, dass der Parameter den Rückgabewert des Members empfängt.|`retval` und `out`|

- **Parametertyp**

  Legt den Datentyp des Parameters fest. Wählen Sie den Typ aus der Liste aus.

- **Parametername**

  Legt den Namen eines Parameters fest, der durch die Methode übergeben werden soll. Wenn Sie den Namen eingegeben haben, müssen Sie auf **Hinzufügen** klicken, um diesen zur Liste der Parameter hinzuzufügen, die durch die Methode übergeben werden. Wenn Sie keinen Parameternamen angeben, ignoriert der Assistent sämtliche ausgewählte Parameterattribute (nur ATL) oder **Parametertypen**.

  Wenn Sie **Hinzufügen** auswählen, wird der Parametername in der **Parameterliste** angezeigt.

  > [!NOTE]
  > Wenn Sie einen Parameternamen angeben und dann **Fertig stellen** auswählen, bevor Sie **Hinzufügen** auswählen, wird der Parameter der Methode nicht hinzugefügt. Sie müssen die Methode suchen und den Parameter manuell einfügen.

- **Add**

  Fügt den Parameter, seinen Typ und seine Parameterattribute der **Parameterliste** hinzu, den Sie in **Parametername** festlegen. Wählen Sie **Hinzufügen** aus, um der Liste einen Parameter hinzuzufügen.

- **Entfernen**

  Entfernt den in der **Parameterliste** ausgewählten Parameter aus der Liste.

- **Parameterliste**

  Zeigt alle Parameter, die derzeit zur Methode hinzugefügt werden, sowie deren Modifizierer und Typen an. Während Sie Parameter hinzufügen, aktualisiert der Assistent die **Parameterliste**, um jeden Parameter einschließlich seiner Modifizierer und Typen anzuzeigen.

## <a name="idl-attributes-add-method-wizard"></a>IDL-Attribute, Assistent zum Hinzufügen von Methoden

Verwenden Sie diese Seite des Assistenten zum Hinzufügen von Methoden, um IDL-Einstellungen (Interface Definiton Language) für die Methode anzugeben.

- `id`

  Legt die numerische ID fest, die die Methode identifiziert. Weitere Informationen finden Sie unter [id](/windows/desktop/Midl/id) in der *MIDL-Referenz*.

  Dieses Feld ist für benutzerdefinierte Schnittstellen und MFC-Disp-Schnittstellen nicht verfügbar.

- `call_as`

  Gibt den Namen einer Remotemethode an, der die lokale Methode zugeordnet werden kann. Weitere Informationen finden Sie unter [call_as](/windows/desktop/Midl/call-as) in der *MIDL-Referenz*.

  Nicht für MFC-Disp-Schnittstellen verfügbar.

- `helpcontext`

  Gibt eine Kontext-ID an, die das Anzeigen von Informationen über diese Methode in der Hilfedatei ermöglicht. Weitere Informationen finden Sie unter [helpcontext](/windows/desktop/Midl/helpcontext) in der *MIDL-Referenz*.

  Nicht für MFC-Disp-Schnittstellen verfügbar.

- `helpstring`

  Gibt eine Zeichenfolge an, die zum Beschreiben des Elements verwendet wird, auf das sie angewendet wird. Sie ist standardmäßig auf „method *Methodenname*“ festgelegt. Weitere Informationen finden Sie unter [helpstring](/windows/desktop/Midl/helpstring) in der *MIDL-Referenz*.

  Nicht für MFC-Disp-Schnittstellen verfügbar.

- **Zusätzliche Attribute**

  Nicht für MFC-Disp-Schnittstellen verfügbar.

  |Attribut|Beschreibung |
  |---------------|-----------------|
  |`hidden`|Gibt an, dass die Methode vorhanden ist, aber nicht in einem benutzerorientierten Browser angezeigt werden sollte. Weitere Informationen finden Sie unter [hidden](/windows/desktop/Midl/hidden) in der *MIDL-Referenz*.|
  |`source`|Gibt an, dass ein Member dieser Methode eine Ereignisquelle ist. Weitere Informationen finden Sie unter [source](/windows/desktop/Midl/source) in der *MIDL-Referenz*.|
  |`local`|Gibt für den MIDL-Compiler an, dass die Methode lokal ist. Weitere Informationen finden Sie unter [local](/windows/desktop/Midl/local) in der *MIDL-Referenz*.|
  |`restricted`|Gibt an, dass die Methode nicht beliebig aufgerufen werden kann. Weitere Informationen finden Sie unter [restricted](/windows/desktop/Midl/restricted) in der *MIDL-Referenz*.|
  |`vararg`|Gibt an, dass die Methode eine variable Anzahl von Argumenten akzeptiert. Das letzte Argument muss ein sicheres Array des Typs `VARIANT` sein, das die übrigen Argumente enthält. Weitere Informationen finden Sie unter [vararg](/windows/desktop/Midl/vararg) in der *MIDL-Referenz*.|
