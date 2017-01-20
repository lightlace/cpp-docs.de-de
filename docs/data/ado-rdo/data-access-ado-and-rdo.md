---
title: "Datenzugriff: ADO und RDO"
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
  - "Gebundene Steuerelemente [C++], ADO"
  - "Gebundene Steuerelemente [C++], RDO"
  - "Steuerelemente [C++], Datenbindung"
  - "Datenzugriff [C++], RDO-Datensteuerelemente"
  - "Datenbindung [C++], ADO"
  - "Datenbindung [C++], RDO"
  - "Datensteuerelemente [C++]"
  - "Datengebundene Steuerelemente [C++], ADO"
  - "Datengebundene Steuerelemente [C++], RDO"
ms.assetid: 92da8f1e-144b-4605-ac0a-43c25bdc14a7
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# Datenzugriff: ADO und RDO
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

In der folgenden Tabelle werden die zwei zugrunde liegenden Technologien dargestellt, die Datenquellen oder datengebundene Steuerelemente unterstützen.  
  
 **ADO**  
 Bei ADO handelt es sich um einen COM\-Wrapper von OLE DB, der das Schreiben von Anwendungen für den Datenzugriff \(Consumern\) erleichtert.  OLE DB ist eine COM\-basierte universelle Datenzugriffstechnologie, die die Verwendung beliebiger \(nicht nur indizierter\) Datenquellen, sequenzieller Zugriffsmethoden \(ISAMs\) sowie SQL\-basierter Datenbanken ermöglicht.  
  
 OLE DB\-Anbieter können auf Daten aus verschiedenen Datenquellen zugreifen. Dabei werden nicht nur SQL\-Abfragen, sondern auch die im Anbieter definierten Abfragen für den Datenabruf verwendet.  
  
 **RDO**  
 RDO ist der COM\-Wrapper von ODBC.  ODBC, eine C\-basierte API, ermöglicht den allgemeinen \(heterogenen\) Datenzugriff.  RDO benötigt jedoch SQL als Befehlssprache für den Datenzugriff.  
  
 Sie sollten daher anstelle der RDO\-basierten Steuerelemente ADO\-basierte Steuerelemente für den Datenzugriff einsetzen.  
  
 In der folgenden Tabelle werden die Hauptunterschiede zwischen den ADO\- und RDO\-Datensteuerelementen dargestellt.  
  
 **Datengebundene Steuerelemente**  
 Datengebundene RDO\-Steuerelemente verwenden die **ICursor**\-Schnittstellen, während ADO\-Steuerelemente die `IRowset`\-Schnittstelle von OLE DB verwenden.  In beiden Fällen geben die von den Steuerelementen verwendeten Schnittstellen ein Rowset zurück.  
  
 Die datengebundenen RDO\-Steuerelemente wurden für den optimalen Einsatz mit Visual Basic entwickelt.  Aus diesem Grund stehen einige Funktionen der datengebundenen RDO\-Steuerelemente, besonders im Bereich der Formatierung, in Visual C\+\+\-Anwendungen nicht zur Verfügung.  Dieses Problem besteht nicht bei ADO\-Datenbindungs\-Steuerelementen.  
  
 **Datensteuerelemente**  
 Durch ADO\-Datensteuerelemente wird die **IDataSource**\-Schnittstelle und durch RDO\-Datensteuerelemente die **IVBDSC**\-Schnittstelle implementiert.  Sie können eine **IDataSource**\-Methode aufrufen, um einen `IRowset`\-Schnittstellenzeiger zu erhalten.  Analog dazu können Sie eine **IVBDSC**\-Methode aufrufen, um einen **ICursor**\-Schnittstellenzeiger zu erhalten.  
  
## Siehe auch  
 [Datenbindung mit ActiveX\-Steuerelementen in Visual C\+\+](../../data/ado-rdo/databinding-with-activex-controls-in-visual-cpp.md)