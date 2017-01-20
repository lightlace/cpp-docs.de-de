---
title: "Festlegen von Eigenschaften im Anbieter"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "OLE DB-Anbieter, Eigenschaften"
  - "Eigenschaften [C++], OLE DB-Anbieter"
ms.assetid: 26a8b493-7ec4-4686-96d0-9ad5d2bca5ac
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Festlegen von Eigenschaften im Anbieter
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Suchen Sie die Eigenschaftengruppe und Eigenschaften\-ID der gewünschten Eigenschaft.  Weitere Informationen finden Sie in der *OLE DB Programmer's Reference* unter [OLE DB Properties](https://msdn.microsoft.com/en-us/library/ms722734.aspx) \(nur auf Englisch verfügbar\).  
  
 Suchen Sie in dem vom Assistenten generierten Anbietercode die Eigenschaftenzuordnung, die der Eigenschaftengruppe entspricht.  Der Name der Eigenschaftengruppe stimmt in der Regel mit dem Objektnamen überein.  Befehls\- und Rowseteigenschaften finden Sie normalerweise im Befehl oder Rowset und Datenquellen\- bzw. Initialisierungseigenschaften im Datenquellenobjekt.  
  
 Fügen Sie der Eigenschaftenzuordnung ein [PROPERTY\_INFO\_ENTRY\_EX](../../data/oledb/property-info-entry-ex.md)\-Makro hinzu.  **PROPERTY\_INFO\_ENTRY\_EX** verfügt über vier Parameter:  
  
-   Die Eigenschaften\-ID der Eigenschaft.  Die ersten sieben Zeichen \("DBPROP\_"\) am Anfang des Eigenschaftennamens müssen entfernt werden.  Wenn Sie beispielsweise **DBPROP\_MAXROWS** hinzufügen möchten, übergeben Sie `MAXROWS` als erstes Element.  Handelt es sich um eine benutzerdefinierte Eigenschaft, übergeben Sie den vollständigen GUID\-Namen \(z. B. `DBMYPROP_MYPROPERTY`\).  
  
-   Den Variantentyp der Eigenschaft \(siehe [OLE DB Properties](https://msdn.microsoft.com/en-us/library/ms722734.aspx) in der *OLE DB Programmer's Reference*, nur auf Englisch verfügbar\).  Geben Sie den **VT\_**\-Typ \(z. B. `VT_BOOL` oder `VT_I2`\) ein, der dem Datentyp entspricht.  
  
-   Flags, die angeben, ob die Eigenschaft Lese\- und Schreiboperationen unterstützt, sowie die Gruppe, zu der sie gehört.  Durch folgenden Code wird beispielsweise eine Lese\-\/Schreibeigenschaft angegeben, die der Rowsetgruppe angehört:  
  
    ```  
    DBPROPFLAGS_ROWSET | DBPROPFLAGS_READ | DBPROPFLAGS_WRITE  
    ```  
  
-   Den Basiswert der Eigenschaft.  Dies kann z. B. **VARIANT\_FALSE** für einen booleschen Typ oder 0 \(null\) für einen ganzzahligen Typ sein.  Der Eigenschaftswert bleibt bis zu seiner Änderung erhalten.  
  
    > [!NOTE]
    >  Einige Eigenschaften sind mit anderen Eigenschaften verbunden oder verkettet, z. B. Lesezeichen\- oder Aktualisierungseigenschaften.  Wenn ein Consumer eine Eigenschaft auf true setzt, sind u. U. auch andere Eigenschaften davon betroffen.  Die OLE DB\-Anbietervorlagen unterstützen diesen Umstand durch die [CUtlProps::OnPropertyChanged](../../data/oledb/cutlprops-onpropertychanged.md)\-Methode.  
  
## Von den OLE DB\-Anbietern von Microsoft ignorierte Eigenschaften  
 Die folgenden OLE DB\-Eigenschaften werden von den OLE DB\-Anbietern von Microsoft ignoriert:  
  
-   **DBPROP\_MAXROWS** ist nur für schreibgeschützte Anbieter geeignet \(bei denen **DBPROP\_IRowsetChange** und **DBPROP\_IRowsetUpdate** den Wert **false** haben\); andernfalls wird diese Eigenschaft nicht unterstützt.  
  
-   **DBPROP\_MAXPENDINGROWS** wird ignoriert; der Anbieter legt eigene Begrenzungen fest.  
  
-   **DBPROP\_MAXOPENROWS** wird ignoriert; der Anbieter legt eigene Begrenzungen fest.  
  
-   **DBPROP\_CANHOLDROWS** wird ignoriert; der Anbieter legt eigene Begrenzungen fest.  
  
## Siehe auch  
 [Arbeiten mit OLE DB\-Anbietervorlagen](../../data/oledb/working-with-ole-db-provider-templates.md)