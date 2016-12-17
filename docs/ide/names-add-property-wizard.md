---
title: "Namen, Assistent zum Hinzuf&#252;gen von Eigenschaften"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "vc.codewiz.prop.overview"
dev_langs: 
  - "C++"
ms.assetid: 0453b7ea-89cb-41a1-80a2-d45f61589c0a
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# Namen, Assistent zum Hinzuf&#252;gen von Eigenschaften
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Verwenden Sie diesen Assistenten, um einer Schnittstelle eine Eigenschaft hinzuzufügen.  
  
 **Eigenschaftentyp**  
 Legt den Typ der Eigenschaft fest, die Sie hinzufügen.  Geben Sie für MFC\-Dispatchschnittstellen einen eigenen Typ an, oder wählen Sie einen Typ aus der vordefinierten Liste aus.  Wenn Sie eine vordefinierte Implementierung einer Eigenschaft angeben, wird **Eigenschaftentyp** auf den vordefinierten Typ gesetzt und kann nicht geändert werden.  
  
 **Eigenschaftenname**  
 Legt den Namen der Eigenschaft fest.  Für mit ActiveX\-Steuerelementen verknüpfte MFC\-Dispatchschnittstellen können Sie einen eigenen Namen angeben oder einen vordefinierten Eigenschaftennamen aus der vordefinierten Liste auswählen.  Wenn Sie einen eigenen Eigenschaftennamen eingeben, ist der Implementierungstyp **Vordefiniert** nicht verfügbar.  Eine Beschreibung der Eigenschaften in der Liste finden Sie unter [Basiseigenschaften](../ide/stock-properties.md).  
  
|Schnittstellentyp|Beschreibung|  
|-----------------------|------------------|  
|Duale ATL\-Schnittstelle, benutzerdefinierte Schnittstelle und lokale benutzerdefinierte Schnittstelle|Geben Sie einen Eigenschaftennamen an.|  
|MFC\-Dispatchschnittstelle, MFC\-ActiveX\-Steuerelement\-Dispatchschnittstelle|Geben Sie einen Eigenschaftennamen an, oder wählen Sie eine Basiseigenschaft aus der Liste aus.  Wenn Sie eine Eigenschaft aus der Liste auswählen, wird im Feld **Eigenschaftentyp** der entsprechende Wert angezeigt.  Je nach Auswahl unter Implementierungstyp können Sie diesen Typ ändern.|  
  
 **Rückgabetyp**  
 Nur ATL\-Schnittstellen.  Legt den Rückgabetyp für die Eigenschaft fest.  Bei dualen Schnittstellen ist der Rückgabetyp immer `HRESULT`, und dieses Feld ist nicht verfügbar.  Bei benutzerdefinierten Schnittstellen können Sie einen Rückgabetyp aus der Liste auswählen.  `HRESULT` wird weiterhin empfohlen, da er als Standardtyp für die Rückgabe von Fehlern gilt.  
  
 **Variablenname**  
 Nur MFC\-Dispatchschnittstellen.  Ist nur verfügbar, wenn Sie unter **Implementierungstyp** die Option **Membervariable** auswählen.  Legt den Namen der Membervariablen fest, mit der die Eigenschaft verknüpft wird.  Der Name der Variablen lautet standardmäßig m\_*Eigenschaftenname*.  Sie können diesen Namen bearbeiten.  
  
 **Benachrichtigungsfunktion**  
 Nur MFC\-Dispatchschnittstellen.  Ist nur verfügbar, wenn Sie unter **Implementierungstyp** die Option **Membervariable** auswählen.  Legt den Namen der Benachrichtigungsfunktion fest, die aufgerufen wird, wenn die Eigenschaft geändert wird.  Der Name der Benachrichtigungsfunktion lautet standardmäßig On*Eigenschaftenname*Changed.  Sie können diesen Namen bearbeiten.  
  
 **Get\-Funktion**  
 Für MFC\-Dispatchschnittstellen.  Ist nur verfügbar, wenn Sie unter **Implementierungstyp** die Option **Get\/Set\-Methoden** auswählen.  Legt den Namen der Funktion fest, mit der die Eigenschaft abgefragt wird.  Der Name der **Get**\-Funktion lautet standardmäßig **Get**Eigenschaftenname.  Sie können diesen Namen bearbeiten.  Wenn Sie den Namen löschen, wird die Funktion [GetNotSupported](../Topic/COleControl::GetNotSupported.md) in die Dispatchzuordnung der Schnittstelle eingefügt.  Die **Get**Eigenschaftenname\-Funktion gibt an, dass die Eigenschaft lesbar ist.  
  
 **Set\-Funktion**  
 Nur MFC\-Dispatchschnittstellen.  Ist nur verfügbar, wenn Sie unter **Implementierungstyp** die Option **Get\/Set\-Methoden** auswählen.  Gibt den Namen der Funktion an, mit der die Eigenschaft festgelegt wird.  Der Name der `Set`\-Funktion lautet standardmäßig `Set`Eigenschaftenname.  Sie können diesen Namen bearbeiten.  Wenn Sie den Namen löschen, wird die Funktion [SetNotSupported](../Topic/COleControl::SetNotSupported.md) in die Dispatchzuordnung der Schnittstelle eingefügt.  Die `Set`Eigenschaftenname\-Funktion gibt an, dass die Eigenschaft schreibbar ist.  
  
 **Implementierungstyp**  
 Nur MFC\-Dispatchschnittstellen.  Legt fest, wie die hinzuzufügende Eigenschaft implementiert wird.  
  
|Implementierungstyp|Beschreibung|  
|-------------------------|------------------|  
|**Vordefiniert**|Legt eine vordefinierte Implementierung für die Eigenschaft fest, die in **Eigenschaftenname** ausgewählt wurde.  Der Standardwert.  Weitere Informationen finden Sie unter [Basiseigenschaften](../ide/stock-properties.md).<br /><br /> Wenn Sie **Vordefiniert** auswählen, werden **Eigenschaftentyp**, **Parametertyp** und **Parametername** abgeblendet.|  
|**Membervariable**|Gibt an, dass die Eigenschaft als Membervariable hinzugefügt wird.  Benutzerdefinierte sowie die meisten Basiseigenschaften können als Membervariablen hinzugefügt werden.  Für die Eigenschaften **Caption**, **hWnd** und **Text** ist die Option **Membervariable** nicht verfügbar.<br /><br /> Unter **Variablenname** und **Benachrichtigungsfunktion** werden Standardnamen bereitgestellt.  Sie können diesen Namen bearbeiten.|  
|**Get\/Set\-Methoden**|Gibt an, dass die Eigenschaft standardmäßig als **Get**Eigenschaftenname\-Funktion und `Set`Eigenschaftenname\-Funktion hinzugefügt wird.  Diese Namen werden unter **Get\-Funktion** und **Set\-Funktion** angezeigt.<br /><br /> Sie können den standardmäßigen **Eigenschaftentyp** ändern, der einen Wert für die **Get**\-Funktion übergibt.  Außerdem können Sie Parameter für die **Get**\-Funktion und die `Set`\-Funktion festlegen.|  
  
 **Get\-Funktion**  
 Für ATL\-Schnittstellen.  Definiert die Eigenschaft als lesbar, d. h., die **Get**\-Methode zum Abrufen dieser Eigenschaft aus dem Objekt wird erstellt.  Sie müssen **Get**, `Put` oder beide Funktionen auswählen.  
  
 **Put\-Funktion**  
 Nur ATL\-Schnittstellen.  Definiert die Eigenschaft als schreibbar, d. h., die `Put`\-Methode zum Festlegen dieser Eigenschaft des Objekts wird erstellt.  Sie müssen **Get**, `Put` oder beide Funktionen auswählen.  Wenn Sie diese Option auswählen, können Sie zwischen den folgenden beiden Optionen zur Implementierung der Methode wählen:  
  
|Option|Beschreibung|  
|------------|------------------|  
|**PropPut**|Die [PropPut](../windows/propput.md)\-Funktion gibt eine Kopie des Objekts zurück.  Dies ist die Standardoption und die einfachste Methode, um die Eigenschaft schreibbar zu machen.|  
|**PropPutRef**|Die [PropPutRef](../windows/propputref.md)\-Funktion gibt anstelle der Objektkopie einen Verweis auf das Objekt zurück.  Die Verwendung dieser Option bietet sich für Objekte wie umfangreiche Strukturen oder Arrays an, deren Initialisierung u. U. aufwendiger ist.|  
  
 **Parameterattribute**  
 Nur ATL\-Schnittstellen.  Legt fest, ob der durch **Parametername** angegebene Parameter **in**, **out**, beides oder keines von beiden ist.  
  
|Option|Beschreibung|  
|------------|------------------|  
|**in**|Gibt an, dass der Parameter von der aufrufenden an die aufgerufene Prozedur übergeben wird.|  
|**out**|Gibt an, dass der Zeigerparameter von der aufgerufenen Prozedur an die aufrufende Prozedur \(d. h. vom Server an den Client\) zurückgegeben wird.|  
  
 **Parametertyp**  
 Legt den Datentyp des Parameters fest.  Wählen Sie den Typ aus der Liste aus.  
  
 **Parametername**  
 Legt den Namen eines Parameters fest, den Sie für die Eigenschaft hinzufügen, falls die Eigenschaft über Parameter verfügt.  Nachdem Sie auf **Hinzufügen** geklickt haben, wird der Parametername in der **Parameterliste** angezeigt.  
  
 **Parameterliste**  
 Zeigt die Liste der Attribute an, die der Eigenschaft hinzugefügt werden sollen.  Jedes Element in der Liste besteht aus dem Parameternamen, dem Parametertyp und Attributen.  Verwenden Sie **Hinzufügen** und **Entfernen**, um die Liste zu aktualisieren.  
  
 **add**  
 Fügt der **Parameterliste** den unter **Parametername** und **Parametertyp** angegebenen Parameter hinzu.  Um einen Parameter in die Liste aufzunehmen, müssen Sie auf **Hinzufügen** klicken.  
  
 **Entfernen**  
 Entfernt den in der **Parameterliste** markierten Parameter.  
  
 **Standardeigenschaft**  
 Nur MFC\-Dispatchschnittstellen.  Definiert diese Eigenschaft als Standardeigenschaft für die Schnittstelle.  Eine Schnittstelle kann nur eine Standardeigenschaft besitzen. Sobald die Standardeigenschaft definiert wurde, ist dieses Feld für weitere Eigenschaften, die Sie der Schnittstelle hinzufügen, nicht mehr verfügbar.  
  
## Siehe auch  
 [Hinzufügen einer Eigenschaft](../ide/adding-a-property-visual-cpp.md)   
 [IDL\-Attribute, Assistent zum Hinzufügen von Eigenschaften](../ide/idl-attributes-add-property-wizard.md)   
 [Implementieren einer Schnittstelle](../ide/implementing-an-interface-visual-cpp.md)