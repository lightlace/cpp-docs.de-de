---
title: "Definieren von gespeicherten Prozeduren | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "OLE DB, Gespeicherte Prozeduren"
  - "Gespeicherte Prozeduren, Definieren"
  - "Gespeicherte Prozeduren, OLE DB"
  - "Gespeicherte Prozeduren, Syntax"
ms.assetid: 54949b81-3275-4dd9-96e4-3eda1ed755f2
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Definieren von gespeicherten Prozeduren
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Bevor Sie eine gespeicherte Prozedur aufrufen können, müssen Sie sie zunächst mithilfe des Makros [DEFINE\_COMMAND](../../data/oledb/define-command.md) definieren.  Wenn Sie den Befehl definieren, geben Sie Parameter mit einem Fragezeichen \(?\) als Parametermarker an:  
  
```  
DEFINE_COMMAND(CMySProcAccessor, _T("{INSERT {name, phone} into shippers  (?,?)}")  
```  
  
 Beachten Sie, dass die in den Codebeispielen in diesem Thema verwendete Syntax \(der Gebrauch von Klammern usw.\) für SQL Server spezifisch ist.  Die in den gespeicherten Prozeduren verwendete Syntax kann sich je nach verwendetem Anbieter hiervon unterscheiden.  
  
 Geben Sie als Nächstes in der Parameterzuordnung die im Befehl verwendeten Parameter an. Listen Sie hierfür die Parameter in der Reihenfolge auf, in der sie im Befehl auftreten:  
  
```  
BEGIN_PARAM_MAP(CMySProcAccessor)  
   SET_PARAM_TYPE(DBPARAMIO_INPUT)  
   COLUMN_ENTRY(1, m_Name)   // name corresponds to first '?' param  
   SET_PARAM_TYPE(DBPARAMIO_INPUT)  
   COLUMN_ENTRY(2, m_Phone)  // phone corresponds to second '?' param  
END_PARAM_MAP()  
```  
  
 Im oben stehenden Beispiel wird eine gespeicherte Prozedur definiert.  Damit Code effizient wiederverwendet werden kann, enthält eine Datenbank einen Satz vordefinierter gespeicherter Prozeduren mit Bezeichnungen wie "Sales by Year" oder "dt\_adduserobject". Sie können die Definitionen mithilfe von SQL Server Enterprise Manager anzeigen.  Der Aufruf erfolgt wie im Folgenden dargestellt. \(Die Position des Parameters '?' hängt von der Schnittstelle der gespeicherten Prozedur ab.\)  
  
```  
DEFINE_COMMAND(CMySProcAccessor, _T("{CALL \"Sales by Year\" (?,?) }")  
DEFINE_COMMAND(CMySProcAccessor, _T("{CALL dbo.dt_adduserobject (?,?) }")  
```  
  
 Deklarieren Sie als Nächstes die Befehlsklasse:  
  
```  
class CMySProc : public CCommand<CAccessor<CMySProcAccessor> >  
```  
  
 Rufen Sie anschließend wie folgt die gespeicherte Prozedur in `OpenRowset` auf:  
  
```  
CSession m_session;  
HRESULT OpenRowset()  
{  
   return CCommand<CAccessor<CMySProcAccessor> >::Open(m_session);  
}  
```  
  
 Beachten Sie auch, dass Sie eine gespeicherte Prozedur mithilfe des Datenbankattributs [db\_command](../../windows/db-command.md) folgendermaßen definieren können:  
  
```  
db_command("{ ? = CALL dbo.dt_adduserobject }")  
```  
  
## Siehe auch  
 [Verwenden von gespeicherten Prozeduren](../../data/oledb/using-stored-procedures.md)