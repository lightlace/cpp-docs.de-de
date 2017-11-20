---
title: "Namen, Eigenschaft Assistent zum Hinzufügen | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.codewiz.prop.overview
dev_langs: C++
ms.assetid: 0453b7ea-89cb-41a1-80a2-d45f61589c0a
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 310ac33fa4e34e75273732f715472114bab9650f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="names-add-property-wizard"></a>Namen, Assistent zum Hinzufügen von Eigenschaften
Verwenden Sie diesen Assistenten, um eine Schnittstelle eine Eigenschaft hinzugefügt.  
  
 **Eigenschaftentyp**  
 Legt den Typ der Eigenschaft, die Sie hinzufügen. Geben Sie für MFC-Dispatchschnittstellen einen eigenen Typ, oder wählen Sie aus der vordefinierten Liste aus. Wenn Sie eine vordefinierte Implementierung einer Eigenschaft bereitstellen **Eigenschaftentyp** ist auf den vordefinierten Typ festgelegt und kann nicht geändert.  
  
 **Eigenschaftenname**  
 Legt den Namen der Eigenschaft fest. Für MFC-Dispatchschnittstellen ActiveX-Steuerelementen zugeordnet können Sie Ihren eigenen Namen angeben, oder können, wählen Sie einen Namen für die Systemeigenschaft aus der vordefinierten Liste. Wenn Sie einen eigenen Eigenschaftennamen angeben der **Stock** Implementierungstyp ist nicht verfügbar. Finden Sie unter [Basiseigenschaften](../ide/stock-properties.md) eine Beschreibung der Eigenschaften in der Liste.  
  
|Schnittstellentyp|Beschreibung|  
|--------------------|-----------------|  
|Duale ATL-Schnittstelle, benutzerdefinierte Schnittstelle und lokale benutzerdefinierte Schnittstelle|Geben Sie einen Eigenschaftennamen.|  
|MFC-Dispinterface, MFC-ActiveX-Steuerelement Disp-Schnittstelle|Geben Sie einen Eigenschaftennamen ein, oder wählen Sie aus der Liste eine Systemeigenschaft. Wenn Sie eine Eigenschaft aus der Liste auswählen, der entsprechende Wert angezeigt wird, der **Eigenschaftentyp** Feld. Sie können dieses Typs ändern, abhängig von Ihrer Auswahl unter **Implementierungstyp**.|  
  
 **Rückgabetyp**  
 Nur ATL-Schnittstellen. Legt den Rückgabetyp für die Eigenschaft fest. Für duale Schnittstellen `HRESULT` ist immer der Rückgabetyp ein, und dieses Feld ist nicht verfügbar. Für benutzerdefinierte Schnittstellen können Sie einen Rückgabetyp aus der Liste auswählen. `HRESULT`wird weiterhin empfohlen, da es sich um ein gängiges Verfahren zum Fehler bereitstellt.  
  
 **Variablenname**  
 MFC nur Disp-Schnittstellen. Nur verfügbar, wenn Sie angeben, **Membervariable** unter **Implementierungstyp**. Legt den Namen der Membervariable, die Eigenschaft zugeordnet ist. Standardmäßig wird der Variablenname m_ festgelegt*PropertyName*. Sie können diesen Namen bearbeiten.  
  
 **Benachrichtigungsfunktion**  
 MFC nur Disp-Schnittstellen. Nur verfügbar, wenn Sie angeben, **Membervariable** unter **Implementierungstyp**. Legt dem Namen der Benachrichtigung aufgerufen wird, wenn die eigenschaftenänderungen an. Wird standardmäßig der Name der Benachrichtigungsfunktion für auf festgelegt ist*PropertyName*geändert. Sie können diesen Namen bearbeiten.  
  
 **Get-Funktion**  
 Für MFC-Dispatchschnittstellen. Nur verfügbar, wenn Sie angeben, **Get/Set-Methoden** unter **Implementierungstyp**. Legt den Namen der Funktion zum Abrufen der Eigenschaft fest. Standardmäßig der Namen der Get-Funktion festgelegt ist, um Get*PropertyName*. Sie können diesen Namen bearbeiten. Wenn Sie den Namen, die Funktion löschen [GetNotSupported](../mfc/reference/colecontrol-class.md#getnotsupported) wird in die Dispatchzuordnung der Schnittstelle eingefügt. Die Get*PropertyName* Funktion gibt an, dass die Eigenschaft lesbar.  
  
 **Set-Funktion**  
 MFC nur Disp-Schnittstellen. Nur verfügbar, wenn Sie angeben, **Get/Set-Methoden** unter **Implementierungstyp**. Legt den Namen der Funktion zum Festlegen der Eigenschaft. Wird standardmäßig der Name des Set-Funktion festgelegt ist, Satz*PropertyName*. Sie können diesen Namen bearbeiten. Wenn Sie den Namen, die Funktion löschen [SetNotSupported](../mfc/reference/colecontrol-class.md#setnotsupported) wird in die Dispatchzuordnung der Schnittstelle eingefügt. Der Satz*PropertyName* -Funktion gibt an, dass die Eigenschaft beschreibbar ist.  
  
 **Implementierungstyp**  
 MFC nur Disp-Schnittstellen. Gibt an, wie die Eigenschaft implementieren, die Sie hinzufügen.  
  
|Implementierungstyp|Beschreibung|  
|-------------------------|-----------------|  
|**Stock**|Gibt eine vordefinierte Implementierung für die Eigenschaft, die im ausgewählten **Eigenschaftsname**. Der Standardwert. Finden Sie unter [Basiseigenschaften](../ide/stock-properties.md) für Weitere Informationen.<br /><br /> Bei Angabe von **Stock**, klicken Sie dann **Eigenschaftentyp**, **Parametertyp**, und **Parametername** sind abgeblendet.|  
|**Membervariablen**|Gibt an, dass die Eigenschaft als Membervariable hinzugefügt wird. Sie können die benutzerdefinierten Eigenschaften oder die meisten Basiseigenschaften als Membervariablen hinzufügen. Sie können keine angeben **Membervariable** für **Beschriftung**, **hWnd**, und **Text** Eigenschaften.<br /><br /> Stellt die Standardnamen unter **Variablenname** und **Benachrichtigungsfunktion**. Sie können diesen Namen bearbeiten.|  
|**Get/Set-Methoden**|Gibt an, die Eigenschaft wird als Get hinzugefügt*PropertyName* und festgelegte*PropertyName* Funktionen, die in der Standardeinstellung. Diese Namen werden unter **Get-Funktion** und **Set-Funktion**.<br /><br /> Sie können die Standardeinstellung ändern **Eigenschaftentyp**, die einen Wert für die Get-Funktion übergibt. Sie können die Parameter zum Angeben der **abrufen** und `Set` Funktionen.|  
  
 **Get-Funktion**  
 Bei ATL-Schnittstellen. Legt die Eigenschaft als lesbar; Das heißt, er erstellt die **abrufen** Methode zum Abrufen dieser Eigenschaft aus dem Objekt. Sie müssen auswählen, **abrufen**, `Put`, oder beides.  
  
 **Put-Funktion**  
 Nur ATL-Schnittstellen. Legt die Eigenschaft beschreibbar; Das heißt, er erstellt die `Put` Methode für das Festlegen oder "Einfügen", diese Eigenschaft des Objekts. Sie müssen auswählen, **abrufen**, `Put`, oder beides. Wenn Sie diese Option auswählen, können Sie von den folgenden zwei Verfahren zur Implementierung der Methode:  
  
|Option|Beschreibung|  
|------------|-----------------|  
|**PropPut**|Die [PropPut](../windows/propput.md) Funktion gibt eine Kopie des Objekts zurück. Dies ist die Standardeinstellung und die gängigste Methode, um die Eigenschaft beschreibbar zu machen.|  
|**PropPutRef**|Die [PropPutRef](../windows/propputref.md) Funktion gibt einen Verweis auf das Objekt, anstatt die Kopie des Objekts selbst zurückgeben. Erwägen Sie diese Option für Objekte, z. B. große Strukturen oder Arrays, die Initialisierung auswirken können.|  
  
 **Parameterattribute**  
 Nur ATL-Schnittstellen. Legt fest, ob der Parameter vom angegebenen **Parametername** ist **in**, **out**, beides oder keines.  
  
|Option|Beschreibung|  
|------------|-----------------|  
|**in**|Gibt an, dass die Parameter an die aufgerufene Prozedur aus der aufrufenden Prozedur übergeben wird.|  
|**out**|Gibt an, dass der Zeigerparameter von der aufgerufenen Prozedur an die aufrufende Prozedur (vom Server an den Client) zurückgegeben wird.|  
  
 **Parametertyp**  
 Legt den Datentyp des Parameters fest. Wählen Sie den Typ aus der Liste aus.  
  
 **Parametername**  
 Legt den Namen eines Parameters, die Sie für die Eigenschaft hinzufügen, wenn die Eigenschaft über Parameter verfügt. Nach dem Klicken auf **hinzufügen**, der Name des Parameters angezeigt wird, im **Parameterliste**.  
  
 **Parameterliste**  
 Zeigt die Liste der Attribute, die die Eigenschaft hinzugefügt werden. Jedes Element in der Liste besteht aus der Parametername, Parametertyp und Attribute. Verwendung **hinzufügen** und **entfernen** zum Aktualisieren der Liste.  
  
 **Add**  
 Fügt die Parameter, die Sie, in angeben **Parametername** und **Parametertyp** auf die **Parameterliste**. Klicken Sie auf **hinzufügen** der Liste einen Parameter hinzu.  
  
 **Entfernen**  
 Entfernt den Parameter, die Sie, in auswählen **Parameterliste**.  
  
 **Standard-Eigenschaft**  
 MFC-Dispinterface nur. Wird diese Eigenschaft als Standard für die Schnittstelle an. Eine Schnittstelle kann nur eine Standardeigenschaft besitzen; Dieses Feld ist nicht verfügbar, nachdem Sie die Standardeigenschaft für alle anderen Eigenschaften angeben, die Sie die Schnittstelle hinzufügen.  
  
## <a name="see-also"></a>Siehe auch  
 [Hinzufügen einer Eigenschaft](../ide/adding-a-property-visual-cpp.md)   
 [IDL-Attribute, hinzufügen Eigenschaft Assistent zum](../ide/idl-attributes-add-property-wizard.md)   
 [Implementieren einer Schnittstelle](../ide/implementing-an-interface-visual-cpp.md)