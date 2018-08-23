---
title: Festlegen von Eigenschaften im Anbieter | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- OLE DB providers, properties
- properties [C++], OLE DB provider
ms.assetid: 26a8b493-7ec4-4686-96d0-9ad5d2bca5ac
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 50f428fa16fee8e1ea545953598fd3f27578310c
ms.sourcegitcommit: a41c4d096afca1e9b619bbbce045b77135d32ae2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2018
ms.locfileid: "42572841"
---
# <a name="setting-properties-in-your-provider"></a>Festlegen von Eigenschaften im Anbieter
Finden Sie die Eigenschaftengruppe und die Eigenschafts-ID für die gewünschte Eigenschaft an. Weitere Informationen finden Sie unter [OLE DB-Eigenschaften](/previous-versions/windows/desktop/ms722734\(v=vs.85\)) in die *OLE DB-Programmierreferenz*.  
  
 Finden Sie in den Anbietercode, die vom Assistenten generiert wird die für die Eigenschaftengruppe eigenschaftenzuordnung ein. Der Name der Eigenschaftengruppe entspricht in der Regel der Name des Objekts. Befehls- und Rowsetobjekte-Eigenschaften finden Sie in den Befehl oder das Rowset; Dateneigenschaften Quell- und Initialisierung finden Sie in das neue Datenquellenobjekt.  
  
 Fügen Sie in der eigenschaftenzuordnung eine [PROPERTY_INFO_ENTRY_EX](../../data/oledb/property-info-entry-ex.md) Makro. PROPERTY_INFO_ENTRY_EX vier Parameter:  
  
-   Die Eigenschafts-ID für Ihre Eigenschaft entspricht. Sie müssen die ersten sieben Zeichen ("DBPROP_") vom Anfang des Namen der Eigenschaft entfernen. Wenn Sie hinzufügen möchten z. B. `DBPROP_MAXROWS`, übergeben Sie `MAXROWS` als erstes Element. Ist dies eine benutzerdefinierte Eigenschaft, übergeben Sie die vollständige GUID-Namen (z. B. `DBMYPROP_MYPROPERTY`).  
  
-   Der variant-Typ der Eigenschaft (in [OLE DB-Eigenschaften](/previous-versions/windows/desktop/ms722734\(v=vs.85\)) in die *OLE DB-Programmierreferenz*). Geben Sie die VT_ Typ (z. B. VT_BOOL oder VT_I2), der Datentyp entspricht.  
  
-   Flags, um anzugeben, ob die Eigenschaft lesbar und schreibbar ist und der Gruppe, zu der er gehört. Der folgende Code gibt beispielsweise an eine Lese-/Schreibeigenschaft, die der Rowset-Gruppe gehören:  
  
    ```  
    DBPROPFLAGS_ROWSET | DBPROPFLAGS_READ | DBPROPFLAGS_WRITE  
    ```  
  
-   Der Basiswert der Eigenschaft. Dies ist möglicherweise `VARIANT_FALSE` Geben Sie für einen booleschen Wert oder 0 (null) für einen ganzzahligen Typ, z. B. Die Eigenschaft weist diesen Wert an, es sei denn, er geändert wird.  
  
    > [!NOTE]
    >  Einige Eigenschaften sind verbunden oder mit anderen Eigenschaften, z. B. Lesezeichen oder Aktualisieren von verkettet. Wenn ein Consumer eine Eigenschaft auf "true" setzt, kann auch eine andere Eigenschaft festgelegt werden. Über die Methode unterstützt die OLE DB-Anbietervorlagen [CUtlProps:: OnPropertyChanged](../../data/oledb/cutlprops-onpropertychanged.md).  
  
## <a name="properties-ignored-by-microsoft-ole-db-providers"></a>Eigenschaften von Microsoft OLE DB-Anbieter ignoriert  
 Der Microsoft OLE DB-Anbieter ignoriert die folgenden OLE DB-Eigenschaften:  
  
-   `DBPROP_MAXROWS` funktioniert nur für schreibgeschützte Anbieter (d. h., in denen DBPROP_IRowsetChange und DBPROP_IRowsetUpdate "false" sind); Andernfalls wird diese Eigenschaft nicht unterstützt.  
  
-   `DBPROP_MAXPENDINGROWS` wird ignoriert. der Anbieter gibt einen eigenen Grenzwert an.  
  
-   `DBPROP_MAXOPENROWS` wird ignoriert. der Anbieter gibt einen eigenen Grenzwert an.  
  
-   `DBPROP_CANHOLDROWS` wird ignoriert. der Anbieter gibt einen eigenen Grenzwert an.  
  
## <a name="see-also"></a>Siehe auch  
 [Arbeiten mit OLE DB-Anbietervorlagen](../../data/oledb/working-with-ole-db-provider-templates.md)