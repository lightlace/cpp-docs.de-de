---
title: "Erfolgreiche Durchf&#252;hrung der OLE&#160;DB-Konformit&#228;tstests | Microsoft Docs"
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
  - "Konformitätstests"
  - "Konformitätstests [OLE DB]"
  - "OLE DB-Anbieter, Testen"
  - "Testen von Anbietern"
  - "Testen, OLE DB-Anbieter"
ms.assetid: d1a4f147-2edd-476c-b452-0e6a0ac09891
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Erfolgreiche Durchf&#252;hrung der OLE&#160;DB-Konformit&#228;tstests
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Das Microsoft Data Access\-SDK umfasst eine Reihe von OLE DB\-Konformitätstests, mit deren Hilfe die Konsistenz von Anbietern gesteigert werden kann.  Die Tests prüfen alle Funktionsaspekte Ihres Anbieters und geben Ihnen die Sicherheit, dass der Anbieter erwartungsgemäß funktioniert.  Sie finden die OLE DB\-Konformitätstests im Microsoft Data Access SDK.  In diesem Abschnitt werden die Schritte zum erfolgreichen Durchführen der Konformitätstests beschrieben.  Informationen zum Ausführen der OLE DB\-Konformitätstests finden Sie im SDK.  
  
## Ausführen der Konformitätstests  
 Die OLE DB\-Anbietervorlagen in Visual C\+\+ 6.0 wurden durch eine Reihe von Verknüpfungsfunktionen erweitert, die die Überprüfung von Werten und Eigenschaften ermöglichen.  Ein Großteil dieser Funktionen wurde als Reaktion auf die Konformitätstests implementiert.  
  
> [!NOTE]
>  Damit der Anbieter die OLE DB\-Konformitätstests besteht, müssen mehrere Validierungsfunktionen hinzugefügt werden.  
  
 Für diesen Anbieter sind zwei Validierungsroutinen erforderlich.  Die erste Routine, `CRowsetImpl::ValidateCommandID`, ist Bestandteil der Rowsetklasse.  Sie wird beim Erstellen des Rowsets durch die Anbietervorlagen aufgerufen.  Im Beispiel wird diese Routine verwendet, um Consumern mitzuteilen, dass keine Indizes unterstützt werden.  Im ersten Schritt wird `CRowsetImpl::ValidateCommandID` aufgerufen \(beachten Sie, dass der Anbieter die **\_RowsetBaseClass**\-Typdefinition verwendet, die der Schnittstellenzuordnung für `CMyProviderRowset` unter [Anbieterunterstützung für Lesezeichen](../../data/oledb/provider-support-for-bookmarks.md) hinzugefügt wurde. Folglich muss diese lange Zeile mit Vorlagenargumenten nicht manuell eingegeben werden\).  Als Nächstes muss **DB\_E\_NOINDEX** zurückgegeben werden, sofern der Indexparameter ungleich **NULL** ist \(dies würde darauf hinweisen, dass der Consumer einen Index verwenden möchte\).  Weitere Informationen zu Befehls\-IDs finden Sie in der OLE DB\-Spezifikation unter **IOpenRowset::OpenRowset**.  
  
 Der folgende Code stellt die **ValidateCommandID**\-Validierungsroutine dar:  
  
```  
/////////////////////////////////////////////////////////////////////  
// MyProviderRS.H  
// Class: CMyProviderRowset   
  
HRESULT ValidateCommandID(DBID* pTableID, DBID* pIndexID)  
{  
   HRESULT hr = _RowsetBaseClass::ValidateCommandID(pTableID, pIndexID);  
   if (hr != S_OK)  
      return hr;  
  
   if (pIndexID != NULL)  
      return DB_E_NOINDEX;    // Doesn't support indexes  
  
   return S_OK;  
}  
```  
  
 Die Anbietervorlagen rufen die `OnPropertyChanged`\-Methode auf, sobald eine Eigenschaft in der **DBPROPSET\_ROWSET**\-Gruppe geändert wird.  Um Eigenschaften für andere Gruppen zu behandeln, fügen Sie diese dem geeigneten Objekt hinzu \(d. h., dass **DBPROPSET\_SESSION**\-Überprüfungen in der `CMyProviderSession`\-Klasse stattfinden\).  
  
 Zuerst wird durch den Code überprüft, ob die Eigenschaft mit einer anderen verknüpft ist.  Wenn die Eigenschaft verkettet ist, wird die **DBPROP\_BOOKMARKS**\-Eigenschaft auf True gesetzt.  In Anhang C der OLE DB\-Spezifikation finden Sie Informationen zu Eigenschaften.  Dort erfahren Sie auch, ob eine Eigenschaft mit einer weiteren Eigenschaft verkettet ist.  
  
 Bei Bedarf können Sie dem Code auch die `IsValidValue`\-Routine hinzufügen.  `IsValidValue` wird von den Vorlagen beim Versuch, eine Eigenschaft festzulegen, aufgerufen.  Wenn beim Festlegen eines Eigenschaftswerts zusätzliche Verarbeitungsschritte erforderlich wären, würden Sie diese Methode überschreiben.  Sie können eine dieser Methoden für jedes Eigenschaftenset verwenden.  
  
## Threadingprobleme  
 Der im ATL\-OLE DB\-Anbieter\-Assistent enthaltene OLE DB\-Anbieter\-Assistent generiert standardmäßig Code für Anbieter, die in einem Apartmentmodell ausgeführt werden.  Wenn Sie versuchen, diesen Code in den Konformitätstests zu verwenden, schlägt die Ausführung zunächst fehl.  Dies liegt daran, dass das für die OLE DB\-Konformitätstests verwendete Tool **Ltm.exe** standardmäßig für das Freethreadingmodell ausgelegt ist.  Der vom OLE DB\-Anbieter\-Assistenten generierte Code verwendet standardmäßig das Apartmentmodell, um höhere Leistung und Benutzerfreundlichkeit zu gewährleisten.  
  
 Um dieses Problem zu beheben, passen Sie entweder LTM oder den Anbieter an.  
  
#### So ändern Sie LTM für die Ausführung im Apartmentthreadmodus  
  
1.  Klicken Sie im Hauptmenü von LTM zunächst auf **Tools** und dann auf **Options**.  
  
2.  Ändern Sie das Threadingmodell auf der Registerkarte **General** von **Free Threaded** in **Apartment Threaded**.  
  
 So ändern Sie den Anbieter für die Ausführung im Freethreadingmodus  
  
-   Suchen Sie im Anbieterprojekt, d. h. in der Datenquelle, der Sitzung und allen Rowsetheadern, nach allen Vorkommen von `CComSingleThreadModel`, und ersetzen Sie diese durch `CComMultiThreadModel`.  
  
-   Ändern Sie das Threadingmodell in der RGS\-Datei von **Apartment** in **Beides**.  
  
-   Befolgen Sie die nötigen Regeln für die Freethreadprogrammierung \(d. h., sperren Sie Schreiboperationen\).  
  
## Siehe auch  
 [Erweiterte Anbietertechniken](../../data/oledb/advanced-provider-techniques.md)