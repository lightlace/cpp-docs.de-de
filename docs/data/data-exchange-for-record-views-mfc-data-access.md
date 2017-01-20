---
title: "Datenaustausch f&#252;r Datensatzansichten (MFC-Datenzugriff)"
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
  - "DDX (Dialog Data Exchange – Dialogdatenaustausch), Datensatzansichten"
  - "DFX (DAO-Datensatzfeldaustausch)"
  - "DFX (DAO-Datensatzfeldaustausch), Datenaustauschmechanismus"
  - "DFX (DAO-Datensatzfeldaustausch), Datensatzansichten"
  - "Datensatzansichten, Datenaustausch"
  - "RFX (Datensatzfeldaustausch)"
  - "RFX (Datensatzfeldaustausch), Datenaustauschmechanismus"
  - "RFX (Datensatzfeldaustausch), Datensatzansichten"
ms.assetid: abc52ca7-6997-47a7-98f3-f347f52b1f72
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# Datenaustausch f&#252;r Datensatzansichten (MFC-Datenzugriff)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wenn Sie mithilfe von [Klasse hinzufügen](../mfc/reference/adding-an-mfc-odbc-consumer.md) die Steuerelemente in der Dialogfeldvorlagen\-Ressource einer Datensatzansicht den Feldern eines Recordsets zuzuordnen, verwaltet das Framework den Datenaustausch in beide Richtungen – vom Recordset zu den Steuerelementen und umgekehrt.  Wenn Sie den DDX\-Mechanismus verwenden, müssen Sie den Code zur Datenübertragung nicht selbst schreiben.  
  
 DDX für Datensatzansichten funktioniert in Verbindung mit:  
  
-   [RFX](../data/odbc/record-field-exchange-rfx.md) für Recordsets der Klasse `CRecordset` \(ODBC\).  
  
-   DFX für Recordsets der Klasse `CDaoRecordset` \(DAO\).  
  
 Obwohl sich ihre Implementierung unterscheidet, ähneln RFX und DFX auf Schnittstellenebene stark den Datenaustauschmechanismen.  Die DAO\-Version „DFX“ ist eng an die ältere ODBC\-Version „RFX“ angelehnt.  Wenn Sie sich mit RFX auskennen, können Sie auch DFX verwenden.  
  
 RFX und DFX verschieben Daten zwischen dem aktuellen Datensatz der Datenquelle und den Felddatenmembern eines Recordset\-Objekts.  DDX verschiebt die Daten aus den Felddatenmembern in die Steuerelemente im Formular.  Durch diese Kombination werden die Steuerelemente des Formulars am Anfang und immer dann gefüllt, wenn der Benutzer sich von Datensatz zu Datensatz bewegt.  Zudem können aktualisierte Daten zurück in das Recordset und anschließend in die Datenquelle verschoben werden.  
  
 Die folgende Abbildung zeigt die Beziehung zwischen DDX und RFX \(oder DFX\) bei Datensatzansichten.  
  
 ![Dialogdatenaustausch und Datensatzfeldaustausch](../data/media/vc37xt1.png "vc37XT1")  
Dialogdatenaustausch und Datensatzfeldaustausch  
  
 Weitere Informationen über DDX finden Sie unter [Dialogdatenaustausch und \-validierung](../mfc/dialog-data-exchange-and-validation.md).  Weitere Informationen über RFX finden Sie unter [Datensatzfeldaustausch \(RFX\)](../data/odbc/record-field-exchange-rfx.md).  
  
## Siehe auch  
 [Datensatzansichten \(MFC\-Datenzugriff\)](../data/record-views-mfc-data-access.md)   
 [Liste der ODBC\-Treiber](../data/odbc/odbc-driver-list.md)