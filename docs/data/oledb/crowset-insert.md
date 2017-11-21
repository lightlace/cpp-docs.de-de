---
title: 'CRowset:: Insert | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL.CRowset<TAccessor>.Insert
- CRowset.Insert
- CRowset<TAccessor>.Insert
- CRowset<TAccessor>::Insert
- ATL::CRowset<TAccessor>::Insert
- ATL.CRowset.Insert
- CRowset::Insert
- ATL::CRowset::Insert
dev_langs: C++
helpviewer_keywords: Insert method
ms.assetid: 6a64a1c3-10ac-4296-8685-0fd6fe63a13b
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: a8cdb6c413cc1a655ace270df632ca501b9b5f3d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="crowsetinsert"></a>CRowset::Insert
Erstellt und initialisiert eine neue Zeile mit Daten aus dem Accessor.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      HRESULT Insert(   
   int nAccessor = 0,   
   bool bGetHRow = false    
) throw( );  
```  
  
#### <a name="parameters"></a>Parameter  
 `nAccessor`  
 [in] Die Anzahl der Accessor zum Einfügen der Daten verwendet werden soll.  
  
 *bGetHRow*  
 [in] Gibt an, ob das Handle für die eingefügte Zeile abgerufen wird.  
  
## <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT`-Objekt.  
  
## <a name="remarks"></a>Hinweise  
 Bei dieser Methode muss die optionale Schnittstelle `IRowsetChange`, die möglicherweise nicht auf allen Anbietern unterstützt, wenn dies der Fall ist, gibt die Methode **E_NOINTERFACE**. Sie müssen auch festlegen **DBPROP_IRowsetChange** auf `VARIANT_TRUE` vor dem Aufruf **öffnen** für die Tabelle oder einen Befehl, der das Rowset enthält.  
  
 INSERT kann fehlschlagen, wenn eine oder mehrere Spalten ist nicht beschreibbar. Ändern Sie die Cursorzuordnung, um diesen Fehler zu beheben.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt, wie der Zugriff auf eine Datenquelle über ein Rowset, und fügen Sie dann eine Zeichenfolge, die Verwendung einer Tabelle in diesem Rowset.  
  
 Erstellen Sie zunächst eine Tabellenklasse, indem ein neues ATL-Objekt in das Projekt eingefügt. Z. B. mit der rechten Maustaste des Projekts im Bereich "Arbeitsbereich", und wählen Sie **neue ATL Object**. Aus der **Datenzugriff** Kategorie wählen **Consumer**. Erstellen Sie ein Consumerobjekt des Typs **Tabelle**. (Auswahl **Tabelle** erstellt ein Rowset direkt aus der Tabelle; auswählen **Befehl** erstellt ein Rowset über einen SQL-Befehl.) Wählen Sie eine Datenquelle, und geben Sie eine Tabelle über den Zugriff auf diese Datenquelle an. Wenn Sie Ihr Consumerobjekt Aufrufen **CCustomerTable**, dann implementieren Sie den Code einfügen wie folgt:  
  
 [!code-cpp[NVC_OLEDB_Consumer#10](../../data/oledb/codesnippet/cpp/crowset-insert_1.cpp)]  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atldbcli.h  
  
## <a name="see-also"></a>Siehe auch  
 [CRowset-Klasse](../../data/oledb/crowset-class.md)