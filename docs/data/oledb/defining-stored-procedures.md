---
title: Definieren von gespeicherten Prozeduren | Microsoft Docs
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
ms.openlocfilehash: 1e03a5ae2e7c75d905216a6be92630376484d047
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="defining-stored-procedures"></a>Definieren von gespeicherten Prozeduren
Bevor Sie eine gespeicherte Prozedur aufrufen, müssen Sie zuerst definieren, mit der [DEFINE_COMMAND](../../data/oledb/define-command.md) Makro. Wenn Sie den Befehl definieren, kennzeichnen Sie Parameter mit einem Fragezeichen (?) als Parametermarker ein:  
  
```  
DEFINE_COMMAND(CMySProcAccessor, _T("{INSERT {name, phone} into shippers  (?,?)}")  
```  
  
 Beachten Sie, dass die in den Codebeispielen in diesem Thema verwendete Syntax (die Verwendung von Klammern usw.) für SQL Server spezifisch ist. Die Syntax, die Sie in den gespeicherten Prozeduren verwenden, kann je nach Anbieter variieren, die Sie verwenden.  
  
 Geben Sie anschließend in der Parameter-Zuordnung zu die Parametern, die Sie im Befehl verwendet, die Parameter in der Reihenfolge im Befehl Auftretens auflisten:  
  
```  
BEGIN_PARAM_MAP(CMySProcAccessor)  
   SET_PARAM_TYPE(DBPARAMIO_INPUT)  
   COLUMN_ENTRY(1, m_Name)   // name corresponds to first '?' param  
   SET_PARAM_TYPE(DBPARAMIO_INPUT)  
   COLUMN_ENTRY(2, m_Phone)  // phone corresponds to second '?' param  
END_PARAM_MAP()  
```  
  
 Im vorherige Beispiel definiert eine gespeicherte Prozedur unter-. Normalerweise enthält der eine Datenbank für die effiziente Wiederverwendung von Code einen Satz von vordefinierten gespeicherte Prozeduren mit Namen wie "Sales by Year" oder "Dt_adduserobject." Sie können die Definitionen mithilfe von SQL Server Enterprise Manager anzeigen. Rufen sie wie folgt (die Platzierung der "?" Parameter hängt von der gespeicherten Prozedur-Schnittstelle):  
  
```  
DEFINE_COMMAND(CMySProcAccessor, _T("{CALL \"Sales by Year\" (?,?) }")  
DEFINE_COMMAND(CMySProcAccessor, _T("{CALL dbo.dt_adduserobject (?,?) }")  
```  
  
 Deklarieren Sie als Nächstes die Befehlsklasse:  
  
```  
class CMySProc : public CCommand<CAccessor<CMySProcAccessor>>  
```  
  
 Rufen Sie anschließend die gespeicherte Prozedur in `OpenRowset` wie folgt:  
  
```  
CSession m_session;  

HRESULT OpenRowset()  
{  
   return CCommand<CAccessor<CMySProcAccessor>>::Open(m_session);  
}  
```  
  
 Beachten Sie, dass Sie eine gespeicherte Prozedur mit dem datenbankattribut definieren können [Db_command](../../windows/db-command.md) wie folgt:  
  
```  
db_command("{ ? = CALL dbo.dt_adduserobject }")  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von gespeicherten Prozeduren](../../data/oledb/using-stored-procedures.md)