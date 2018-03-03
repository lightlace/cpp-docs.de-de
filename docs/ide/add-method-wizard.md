---
title: "Assistent zum Hinzufügen | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.codewiz.method.overview
dev_langs:
- C++
helpviewer_keywords:
- Add Method Wizard [C++]
- methods [C++], adding using wizards
ms.assetid: b9a71b0e-9ecf-40fa-9f86-4200cb23d671
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 63595fe7fda434b7ee16161bd3afdaf8a46fad82
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="add-method-wizard"></a>Assistent zum Hinzufügen von Methoden
Verwenden Sie diesen Assistenten, einer Schnittstelle eine Methode hinzu. Je nach Projekttyp oder Schnittstellentyp, der Sie eine Methode hinzufügen, zeigt der Assistent unterschiedliche Optionen an.  
  
## <a name="names"></a>Namen  
 **Rückgabetyp**  
 Der Datentyp, der von der Methode zurückgegeben wird. `HRESULT`wird für alle Schnittstellentypen empfohlen werden, da es ein gängiges Verfahren zur Rückgabe von Fehlern bietet.  
  
|Schnittstellentyp|Beschreibung|  
|--------------------|-----------------|  
|Duale Schnittstelle|`HRESULT` Nicht geändert werden.|  
|Benutzerdefinierte Schnittstelle|`HRESULT` Nicht geändert werden.|  
|Lokale benutzerdefinierte Schnittstelle|Geben Sie Ihre eigenen Rückgabetyp an, oder wählen Sie aus der Liste aus.|  
|Disp-Schnittstelle|Geben Sie Ihre eigenen Rückgabetyp an, oder wählen Sie aus der Liste aus.|  
|MFC-ActiveX-Steuerelement Disp-Schnittstelle|Wenn Sie eine vordefinierte Methode implementieren, wird der Rückgabetyp wird auf den entsprechenden Wert festgelegt und kann nicht geändert werden. Bei Auswahl eine Methode aus der **Methodennamen** aus, und klicken Sie auf **benutzerdefinierte** unter **Methodentyp wählen**, wählen Sie aus der Liste einen Rückgabetyp aufweisen.|  
  
 **Methodenname**  
 Legt den Namen für die Methode fest.  
  
|Schnittstellentyp|Beschreibung|  
|--------------------|-----------------|  
|Duale ATL-Schnittstelle, benutzerdefinierte Schnittstelle und lokale benutzerdefinierte Schnittstelle|Geben Sie den Methodennamen Ihrer eigenen.|  
|MFC-Disp-Schnittstelle|Geben Sie einen eigene Methode an, oder wählen Sie einen Namen für die vorgeschlagene Methode aus der Liste aus. Wenn Sie einen Namen aus der Liste auswählen, der entsprechende Wert wird angezeigt, der **Rückgabetyp** Feld, und es kann nicht geändert werden.|  
|MFC-ActiveX-Steuerelement Disp-Schnittstelle|Geben Sie einen eigenen, oder wählen Sie eine der vordefinierten Methoden [DoClick](../mfc/reference/colecontrol-class.md#doclick) und [aktualisieren](../mfc/reference/colecontrol-class.md#refresh). Finden Sie unter [MFC-ActiveX-Steuerelemente: Hinzufügen der Stock-Methoden](../mfc/mfc-activex-controls-adding-stock-methods.md) für Weitere Informationen.|  
  
 **Methodentyp**  
 Verfügbar nur für MFC-ActiveX-Steuerelemente. Wenn Sie den Namen einer Methode im Angeben der **Methodennamen** Feld, anstatt eine Methode in der Liste auszuwählen, ist dieses Kontrollkästchen nicht verfügbar.  
  
 Bei Auswahl einer der Methoden in der **Methodennamen** , wählen Sie entweder die vordefinierte Implementierung oder eine benutzerdefinierte Implementierung.  
  
|Methodentyp|Beschreibung|  
|-----------------|-----------------|  
|**Stock**|Der Standardwert. Fügt die vordefinierte Implementierung der Methode, die Sie, in Auswählen der **Methodennamen** Liste. **Rückgabetyp** kann nicht geändert werden, wenn Sie die Option **Stock**.|  
|**Benutzerdefiniert**|Fügt die Methode in eine Stubimplementierung der **Methodennamen** Liste. Für benutzerdefinierte Methodentypen, können Sie Ihre eigenen Rückgabetyp angeben, oder wählen Sie einen aus der **Rückgabetyp** Liste.|  
  
 **Interner name**  
 Verfügbar nur für benutzerdefinierte Methoden eine MFC-Dispinterface hinzugefügt werden soll. Legt den Namen in die Dispatchzuordnung der Headerdatei (. h) und der Implementierungsdatei (.cpp) verwendet. Dieser Name wird standardmäßig identisch **Methodennamen**. Sie können den Methodennamen ändern, wenn mit einer MFC-Dispinterface Arbeit oder wenn Sie eine benutzerdefinierte Methode, ein MFC-ActiveX-Steuerelement Dispinterface hinzufügen.  
  
|Schnittstellentyp|Beschreibung|  
|--------------------|-----------------|  
|Duale ATL-Schnittstelle, benutzerdefinierte Schnittstelle und lokale benutzerdefinierte Schnittstelle|Nicht verfügbar|  
|MFC-Disp-Schnittstelle|Der Name der Methode standardmäßig festgelegt. Sie können den internen Namen bearbeiten.|  
|MFC-ActiveX-Steuerelement Disp-Schnittstelle|Sie können den internen Namen für die benutzerdefinierten Methoden festlegen. Stock-Methoden verwenden Sie einen internen Namen.|  
  
 **Parameterattribute**  
 Legt alle zusätzlichen Attribute für Parameter, die im angegebenen **Parametername**.  
  
|Parameterattribut|Beschreibung|Zulässige Kombinationen|  
|-------------------------|-----------------|--------------------------|  
|**In**|Gibt an, dass die Parameter an die aufgerufene Prozedur aus der aufrufenden Prozedur übergeben wird.|**in** nur<br /><br /> **in** und **out**|  
|**Out**|Gibt an, dass der Zeigerparameter von der aufgerufenen Prozedur an die aufrufende Prozedur (vom Server an den Client) zurückgegeben wird.|**out** nur<br /><br /> **in** und **out**<br /><br /> **out** und **Retval**|  
|**Retval**|Gibt an, dass der Parameter den Rückgabewert des Members empfängt.|**Retval** und Out|  
  
 **Parametertyp**  
 Legt den Datentyp des Parameters fest. Wählen Sie den Typ aus der Liste aus.  
  
 **Parametername**  
 Legt den Namen eines Parameters, durch die Methode übergeben. Klicken Sie nach Eingabe des Namens, Sie müssen auf **hinzufügen** die Liste der Parameter hinzuzufügen, die durch die Methode übergeben wird. Wenn Sie einen Parameternamen nicht angeben, ignoriert der Assistent alle Parameterattribute (nur ATL) oder **Parametertyp** Auswahl.  
  
 Nach dem Klicken auf **hinzufügen**, der Name des Parameters angezeigt wird, im **Parameterliste**.  
  
 **Hinweis** Wenn Sie einen Parameternamen angeben, und klicken Sie dann auf **Fertig stellen** klicken Sie erst **hinzufügen**, der Parameter wird nicht an die Methode hinzugefügt. Sie müssen suchen Sie die Methode, und fügen Sie den Parameter manuell.  
  
 **Add**  
 Fügt die Parameter, die Sie, in angeben **Parametername**, und die zugehörigen Attribute Typ und Parameter zum **Parameterliste**. Klicken Sie auf **hinzufügen** der Liste einen Parameter hinzu.  
  
 **Entfernen**  
 Entfernt den Parameter, die Sie, in auswählen **Parameterliste** aus der Liste.  
  
 **Parameterliste**  
 Zeigt alle Parameter, den Modifizierern und Typen, die derzeit für die Methode hinzugefügt. Wenn Sie Parameter hinzufügen, wird der Assistent aktualisiert **Parameterliste** jeden Parameter mit dem zugehörigen Modifizierer und Typ angezeigt.  
  
## <a name="see-also"></a>Siehe auch  
 [Hinzufügen einer Methode](../ide/adding-a-method-visual-cpp.md)   
 [IDL-Attribute, Assistent zum Hinzufügen von Methoden](../ide/idl-attributes-add-method-wizard.md)