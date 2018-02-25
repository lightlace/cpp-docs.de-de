---
title: Festlegen von Eigenschaften im Anbieter | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- OLE DB providers, properties
- properties [C++], OLE DB provider
ms.assetid: 26a8b493-7ec4-4686-96d0-9ad5d2bca5ac
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 92c5128e3df1e2dfebfef338f3505201cfc40671
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="setting-properties-in-your-provider"></a>Festlegen von Eigenschaften im Anbieter
Suchen Sie die Eigenschaftsgruppe und die Eigenschafts-ID für die gewünschte Eigenschaft. Weitere Informationen finden Sie unter [OLE DB-Eigenschaften](https://msdn.microsoft.com/en-us/library/ms722734.aspx) in der *OLE DB Programmer's Reference*.  
  
 Finden Sie in den Anbietercode, die vom Assistenten generiert wird die entsprechend der Eigenschaftengruppe eigenschaftenzuordnung. Der Name der Gruppe "Eigenschaft" entspricht normalerweise der Name des Objekts. Befehls- und Rowsetobjekte Eigenschaften können im Befehl oder Rowset nicht gefunden werden; Dateneigenschaften Quell- und Initialisierung finden Sie in das Datenquellenobjekt.  
  
 Fügen Sie in der eigenschaftenzuordnung eine [PROPERTY_INFO_ENTRY_EX](../../data/oledb/property-info-entry-ex.md) Makro. PROPERTY_INFO_ENTRY_EX vier Parameter:  
  
-   Die Eigenschafts-ID der Eigenschaft. Sie müssen die ersten sieben Zeichen ("DBPROP_") am Anfang der Eigenschaftsname entfernen. Angenommen, Sie hinzufügen möchten **DBPROP_MAXROWS**, übergeben Sie `MAXROWS` als erstes Element. Wenn dies eine benutzerdefinierte Eigenschaft ist, übergeben Sie den vollständigen Namen der GUID (z. B. `DBMYPROP_MYPROPERTY`).  
  
-   Variant-Typ der Eigenschaft (in [OLE DB-Eigenschaften](https://msdn.microsoft.com/en-us/library/ms722734.aspx) in der *OLE DB Programmer's Reference*). Geben Sie die **VT_** Typ (z. B. `VT_BOOL` oder `VT_I2`) in den Datentyp entspricht.  
  
-   Flags, um anzugeben, ob die Eigenschaft lesbar und beschreibbar ist und die Gruppe, zu der er gehört. Der folgende Code gibt beispielsweise an eine Lese-/Schreibzugriff-Eigenschaft, die der Rowset-Gruppe gehören:  
  
    ```  
    DBPROPFLAGS_ROWSET | DBPROPFLAGS_READ | DBPROPFLAGS_WRITE  
    ```  
  
-   Der Basiswert der Eigenschaft. Dies ist möglicherweise **VARIANT_FALSE** geben einen booleschen Wert ab, oder 0 (null) für einen ganzzahligen Typ, z. B. Die Eigenschaft weist diesen Wert an, es sei denn, er geändert wird.  
  
    > [!NOTE]
    >  Einige Eigenschaften sind verbunden oder mit anderen Eigenschaften, z. B. Lesezeichen oder Aktualisieren von verkettet. Wenn ein Consumer eine Eigenschaft auf True festgelegt, kann auch eine andere Eigenschaft festgelegt werden. Der OLE DB-Anbietervorlagen unterstützt diese mithilfe der Methode [CUtlProps:: OnPropertyChanged](../../data/oledb/cutlprops-onpropertychanged.md).  
  
## <a name="properties-ignored-by-microsoft-ole-db-providers"></a>Eigenschaften von Microsoft OLE DB-Anbieter ignoriert  
 Microsoft OLE DB-Anbieter ignoriert die folgenden OLE DB-Eigenschaften:  
  
-   **DBPROP_MAXROWS** funktioniert nur für schreibgeschützte Anbieter (d. h., in denen DBPROP_IRowsetChange und DBPROP_IRowsetUpdate "false" werden); andernfalls wird diese Eigenschaft nicht unterstützt.  
  
-   **DBPROP_MAXPENDINGROWS** ignoriert wird, der Anbieter gibt einen eigenen Grenzwert.  
  
-   **DBPROP_MAXOPENROWS** ignoriert wird, der Anbieter gibt einen eigenen Grenzwert.  
  
-   **DBPROP_CANHOLDROWS** ignoriert wird, der Anbieter gibt einen eigenen Grenzwert.  
  
## <a name="see-also"></a>Siehe auch  
 [Arbeiten mit OLE DB-Anbietervorlagen](../../data/oledb/working-with-ole-db-provider-templates.md)