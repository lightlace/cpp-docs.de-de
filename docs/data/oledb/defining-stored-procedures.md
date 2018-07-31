---
title: Definieren von gespeicherten Prozeduren | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- stored procedures, syntax
- OLE DB, stored procedures
- stored procedures, defining
- stored procedures, OLE DB
ms.assetid: 54949b81-3275-4dd9-96e4-3eda1ed755f2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 2856418da13cc80d47c10295234b47813071a4ec
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2018
ms.locfileid: "39336952"
---
# <a name="defining-stored-procedures"></a>Definieren von gespeicherten Prozeduren
Bevor Sie eine gespeicherte Prozedur aufrufen, müssen Sie zuerst definieren, mit der [DEFINE_COMMAND](../../data/oledb/define-command.md) Makro. Wenn Sie den Befehl definieren, zu kennzeichnen Sie Parametern mit einem Fragezeichen (?) als parametermarkierung:  
  
```  
DEFINE_COMMAND(CMySProcAccessor, _T("{INSERT {name, phone} into shippers  (?,?)}")  
```  
  
 Beachten Sie, dass die in den Codebeispielen in diesem Thema verwendete Syntax (die Verwendung von Klammern usw.) für SQL Server spezifisch ist. Die Syntax, die Sie in den gespeicherten Prozeduren verwenden variieren nach Anbieter, die Sie verwenden.  
  
 Geben Sie als Nächstes in der parameterzuordnung und die Parameter, die Sie im Befehl verwendet, die Parameter in der Reihenfolge, in die Zeitpunkte im Befehl auflisten:  
  
```  
BEGIN_PARAM_MAP(CMySProcAccessor)  
   SET_PARAM_TYPE(DBPARAMIO_INPUT)  
   COLUMN_ENTRY(1, m_Name)   // name corresponds to first '?' param  
   SET_PARAM_TYPE(DBPARAMIO_INPUT)  
   COLUMN_ENTRY(2, m_Phone)  // phone corresponds to second '?' param  
END_PARAM_MAP()  
```  
  
 Im vorherigen Beispiel wird eine gespeicherte Prozedur definiert, wie es geht. In der Regel enthält der eine Datenbank für die effiziente Wiederverwendung von Code eine Reihe von vordefinierten gespeicherten Prozeduren mit Namen wie "Sales by Year" oder "Dt_adduserobject." Sie können die Definitionen mithilfe von SQL Server Enterprise Manager anzeigen. Rufen sie wie folgt (die Platzierung von der '?' Parameter hängt von der gespeicherten Prozedur-Schnittstelle):  
  
```  
DEFINE_COMMAND(CMySProcAccessor, _T("{CALL \"Sales by Year\" (?,?) }")  
DEFINE_COMMAND(CMySProcAccessor, _T("{CALL dbo.dt_adduserobject (?,?) }")  
```  
  
 Im nächsten Schritt deklariere die Klasse des Befehls:  
  
```cpp  
class CMySProc : public CCommand<CAccessor<CMySProcAccessor>>  
```  
  
 Schließlich rufen Sie die gespeicherte Prozedur im `OpenRowset` wie folgt:  
  
```cpp  
CSession m_session;  

HRESULT OpenRowset()  
{  
   return CCommand<CAccessor<CMySProcAccessor>>::Open(m_session);  
}  
```  
  
 Beachten Sie, dass Sie eine gespeicherte Prozedur, die mit dem datenbankattribut definieren können [Db_command](../../windows/db-command.md) wie folgt:  
  
```cpp  
db_command("{ ? = CALL dbo.dt_adduserobject }")  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von gespeicherten Prozeduren](../../data/oledb/using-stored-procedures.md)