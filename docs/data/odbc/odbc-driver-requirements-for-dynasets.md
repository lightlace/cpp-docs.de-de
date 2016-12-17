---
title: "ODBC-Treiberanforderungen f&#252;r Dynasets"
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
  - "Treiber, Für Dynasets"
  - "Treiber, ODBC"
  - "Dynasets"
  - "ODBC-Treiber, Dynasets"
  - "ODBC-Recordsets, Dynasets"
  - "Recordsets, Dynasets"
ms.assetid: 585cc67b-4d92-404b-9903-d769cd17badc
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# ODBC-Treiberanforderungen f&#252;r Dynasets
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

In den MFC\-ODBC\-Datenbankklassen sind Dynasets Recordsets mit dynamischen Eigenschaften, die auf bestimmte Weise mit den Datenquellen synchronisiert bleiben.  MFC\-Dynasets \(jedoch keine reinen Vorwärts\-Recordsets\) setzen einen Level 2\-API\-konformen ODBC\-Treiber voraus.  Falls der Treiber für die [Datenquelle](../../data/odbc/data-source-odbc.md) dem Level 1\-API\-Satz entspricht, können Sie zwar aktualisierbare, schreibgeschützte Momentaufnahmen und Vorwärts\-Recordsets verwenden, jedoch keine Dynasets.  Ein Level 1\-Treiber kann allerdings Dynasets unterstützen, falls er erweiterte Abrufe und keysetgesteuerte Cursor unterstützt.  
  
 In der ODBC\-Terminologie werden Dynasets und Momentaufnahmen als Cursor bezeichnet.  Ein Cursor ist ein Tool, um die Position innerhalb eines Recordsets zu verwalten.  Weitere Informationen über Treiberanforderungen für Dynasets finden Sie unter [Dynaset](../../data/odbc/dynaset.md).  Weitere Informationen über Cursor finden Sie im [Open Database Connectivity \(ODBC\)](https://msdn.microsoft.com/en-us/library/ms710252.aspx)\-SDK in der MSDN\-Dokumentation.  
  
> [!NOTE]
>  Für aktualisierbare Recordsets muss der ODBC\-Treiber entweder positionierbare Aktualisierungsanweisungen oder die **::SQLSetPos**\-ODBC\-API\-Funktion unterstützen.  Werden beide unterstützt, verwendet MFC aus Effizienzgründen **::SQLSetPos**.  Für Momentaufnahmen können Sie alternativ auch die Cursorbibliothek einsetzen, die die erforderliche Unterstützung für aktualisierbare Momentaufnahmen bietet \(statische Cursor und positionierbare Aktualisierungsanweisungen\).  
  
## Siehe auch  
 [Grundlagen zu ODBC](../../data/odbc/odbc-basics.md)