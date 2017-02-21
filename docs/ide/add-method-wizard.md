---
title: "Assistent zum Hinzuf&#252;gen von Methoden | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.codewiz.method.overview"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Assistent zum Hinzufügen von Methoden [C++]"
  - "Methoden [C++], Hinzufügen mit Assistenten"
ms.assetid: b9a71b0e-9ecf-40fa-9f86-4200cb23d671
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Assistent zum Hinzuf&#252;gen von Methoden
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Verwenden Sie diesen Assistenten, um einer Schnittstelle eine Methode hinzuzufügen.  Je nach Projekttyp oder Schnittstellentyp, dem Sie eine Methode hinzufügen, zeigt der Assistent unterschiedliche Optionen an.  
  
## Namen  
 **Rückgabetyp**  
 Der von der Methode zurückgegebene Datentyp.  Für alle Schnittstellentypen wird `HRESULT` empfohlen, da er als Standardtyp für die Rückgabe von Fehlern gilt.  
  
|Schnittstellentyp|Beschreibung|  
|-----------------------|------------------|  
|Duale Schnittstelle|`HRESULT`.  Kann nicht geändert werden.|  
|Benutzerdefinierte Schnittstelle|`HRESULT`.  Kann nicht geändert werden.|  
|Lokale benutzerdefinierte Schnittstelle|Geben Sie einen eigenen Rückgabetyp an, oder wählen Sie einen Typ aus der Liste aus.|  
|Dispatchschnittstelle|Geben Sie einen eigenen Rückgabetyp an, oder wählen Sie einen Typ aus der Liste aus.|  
|MFC\-ActiveX\-Steuerelement\-Dispatchschnittstelle|Wenn Sie eine vordefinierte Methode implementieren, wird der Rückgabetyp auf den entsprechenden Wert gesetzt und kann nicht geändert werden.  Wenn Sie eine Methode aus der Liste **Methodenname** auswählen und unter **Wählen Sie den Methodentyp** auf **Benutzerdefiniert** klicken, wählen Sie einen Rückgabetyp aus der Liste aus.|  
  
 **Methodenname**  
 Legt den Namen für die Methode fest.  
  
|Schnittstellentyp|Beschreibung|  
|-----------------------|------------------|  
|Duale ATL\-Schnittstelle, benutzerdefinierte Schnittstelle und lokale benutzerdefinierte Schnittstelle|Geben Sie einen eigenen Methodennamen an.|  
|MFC\-Dispatchschnittstelle|Geben Sie einen eigenen Methodennamen an, oder wählen Sie einen vorgeschlagenen Methodennamen aus der Liste aus.  Wenn Sie einen Namen aus der Liste auswählen, wird im Feld **Rückgabetyp** der entsprechende, unveränderliche Wert angezeigt.|  
|MFC\-ActiveX\-Steuerelement\-Dispatchschnittstelle|Geben Sie einen eigenen Methodennamen an, oder wählen Sie eine der vordefinierten Methoden [DoClick](../Topic/COleControl::DoClick.md) oder [Refresh](../Topic/COleControl::Refresh.md) aus.  Weitere Informationen finden Sie unter [MFC\-ActiveX\-Steuerelemente: Hinzufügen vordefinierter Methoden](../mfc/mfc-activex-controls-adding-stock-methods.md).|  
  
 **Methodentyp**  
 Nur für MFC\-ActiveX\-Steuerelemente verfügbar.  Wenn Sie im Feld **Methodenname** einen Methodennamen eingeben, anstatt eine Methode aus der Liste auszuwählen, ist dieses Feld nicht verfügbar.  
  
 Wenn Sie eine der Methoden aus der Liste **Methodenname** auswählen, wählen Sie entweder die vordefinierte Implementierung oder eine benutzerdefinierte Implementierung aus.  
  
|Methodentyp|Beschreibung|  
|-----------------|------------------|  
|**Vordefiniert**|Der Standardwert.  Fügt die vordefinierte Implementierung der Methode ein, die Sie in der Liste **Methodenname** ausgewählt haben.  Wenn Sie **Vordefiniert** auswählen, kann der Rückgabetyp nicht geändert werden.|  
|**Benutzerdefiniert**|Fügt eine Stubimplementierung der Methode ein, die in der Liste **Methodenname** ausgewählt wurde.  Für benutzerdefinierte Methodentypen können Sie einen eigenen Rückgabetyp angeben oder einen Eintrag aus der Liste **Rückgabetyp** auswählen.|  
  
 **Interner Name**  
 Nur für benutzerdefinierte Methoden verfügbar, die einer MFC\-Dispatchschnittstelle hinzugefügt wurden.  Legt den in der Dispatchzuordnung verwendeten Namen, die Headerdatei \(**.h**\) und die Implementierungsdatei \(**.cpp**\) fest.  Dieser Name stimmt standardmäßig mit dem **Methodennamen** überein.  Sie können den Methodennamen ändern, wenn Sie mit einer MFC\-Dispatchschnittstelle arbeiten oder einer MFC\-ActiveX\-Steuerelement\-Dispatchschnittstelle eine benutzerdefinierte Methode hinzufügen.  
  
|Schnittstellentyp|Beschreibung|  
|-----------------------|------------------|  
|Duale ATL\-Schnittstelle, benutzerdefinierte Schnittstelle und lokale benutzerdefinierte Schnittstelle|Nicht verfügbar|  
|MFC\-Dispatchschnittstelle|Entspricht standardmäßig dem Methodennamen.  Der interne Name kann bearbeitet werden.|  
|MFC\-ActiveX\-Steuerelement\-Dispatchschnittstelle|Der interne Name kann nur für benutzerdefinierte Methoden festgelegt werden.  Für vordefinierte Methoden werden keinen internen Namen verwendet.|  
  
 **Parameterattribute**  
 Legt alle zusätzlichen Attribute für Parameter fest, die in **Parametername** angegeben sind.  
  
|Parameterattribut|Beschreibung|Zulässige Kombinationen|  
|-----------------------|------------------|-----------------------------|  
|**In**|Gibt an, dass der Parameter von der aufrufenden an die aufgerufene Prozedur übergeben wird.|nur **in**<br /><br /> **in** und **out**|  
|**Out**|Gibt an, dass der Zeigerparameter von der aufgerufenen Prozedur an die aufrufende Prozedur \(d. h. vom Server an den Client\) zurückgegeben wird.|nur **out**<br /><br /> **in** und **out**<br /><br /> **out** und **retval**|  
|**Retval**|Gibt an, dass der Parameter den Rückgabewert des Members erhält.|**retval** und **out**|  
  
 **Parametertyp**  
 Legt den Datentyp des Parameters fest.  Wählen Sie den Typ aus der Liste aus.  
  
 **Parametername**  
 Legt den Namen eines Parameters fest, der durch die Methode übergeben wird.  Nach der Eingabe des Namens müssen Sie auf **Hinzufügen** klicken, um den Namen in die Liste der Parameter aufzunehmen, die durch die Methode übergeben werden.  Wenn Sie keinen Parameternamen angeben, ignoriert der Assistent alle Parameterattribute \(nur ATL\) oder unter **Parametertyp** ausgewählten Optionen.  
  
 Nachdem Sie auf **Hinzufügen** geklickt haben, wird der Parametername in der **Parameterliste** angezeigt.  
  
 **Hinweis** Wenn Sie einen Parameternamen angeben und dann zuerst auf **Fertig stellen** anstatt auf **Hinzufügen** klicken, wird der Parameter der Methode nicht hinzugefügt.  In diesem Fall müssen Sie die Methode suchen und den Parameter manuell einfügen.  
  
 **add**  
 Fügt den unter **Parametername** angegebenen Parameter sowie dessen Typ und Parameterattribute der **Parameterliste** hinzu.  Um einen Parameter in die Liste aufzunehmen, müssen Sie auf **Hinzufügen** klicken.  
  
 **Entfernen**  
 Entfernt den in der **Parameterliste** ausgewählten Parameter aus der Liste.  
  
 **Parameterliste**  
 Zeigt alle Parameter, deren Modifizierer und Typen an, die der Methode derzeit hinzugefügt sind.  Während Sie Parameter hinzufügen, aktualisiert der Assistent die **Parameterliste** und zeigt jeden Parameter mit dem zugehörigen Modifizierer und Typ an.  
  
## Siehe auch  
 [Hinzufügen einer Methode](../ide/adding-a-method-visual-cpp.md)   
 [IDL\-Attribute, Assistent zum Hinzufügen von Methoden](../ide/idl-attributes-add-method-wizard.md)