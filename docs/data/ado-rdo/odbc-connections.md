---
title: "ODBC-Verbindungen | Microsoft Docs"
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
  - "ODBC-Verbindungen, Konfigurieren"
  - "ODBC, Konnektivität"
ms.assetid: c9df2fa6-d9e2-4335-b885-724662968691
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# ODBC-Verbindungen
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ODBC\-Verbindungen werden in der Systemsteuerung konfiguriert.  Sie können mit allen Datenquellen hergestellt werden, für die ein ODBC\-Treiber installiert wurde.  Visual C\+\+ 6.0 oder höhere Versionen bieten Treiber für Textdateien sowie für Access, FoxPro, Paradox, dBASE, Excel, SQL Server und Oracle.  Wenn Sie eine ODBC\-Verbindung herstellen, erhält diese automatisch einen Datenquellennamen \(DSN, Data Source Name\).  Der DSN wird anschließend zur Identifizierung von Verbindungen in Datensteuerelementen, wie dem ADO\-Datensteuerelement und dem RDO\-Remote\-Datensteuerelement, verwendet.  
  
 **OLE DB\-Verbindungen** Für die Konfiguration einer OLE DB\-Verbindung sind keine zusätzlichen Schritte notwendig.  Wenn Sie eine ODBC\-Datenquelle erstellen, wird diese beispielsweise automatisch vom OLE DB\-Anbieter für ODBC erkannt.  
  
### So konfigurieren Sie eine ODBC\-Datenquelle  
  
1.  Klicken Sie auf **Start**, auf **Einstellungen** und dann auf **Systemsteuerung**.  
  
2.  Wählen Sie in der Systemsteuerung 32\-Bit\-ODBC \(Windows 95 oder 98\) oder ODBC \(Windows NT oder 2000\).  
  
3.  Klicken Sie auf die Registerkarte **Benutzer\-DSN** oder **System\-DSN**.  Die Option **Benutzer\-DSN** ermöglicht die Erstellung benutzerspezifischer Datenquellennamen, und die Option **System\-DSN** ermöglicht die Erstellung von Datenquellen, die allen Benutzern zur Verfügung stehen.  
  
4.  Klicken Sie auf **Hinzufügen**, um eine Liste der lokal installierten ODBC\-Treiber anzuzeigen.  
  
5.  Wählen Sie den Treiber aus, der dem ISAM \(Indexed Sequential Access Method\)\-Typ oder Datenbanktyp entspricht, mit dem Sie eine Verbindung herstellen möchten, und klicken Sie dann auf **Fertig stellen**.  
  
6.  Folgen Sie den treiberspezifischen Anweisungen.  Nach Beendigung dieses Vorgangs ist der DSN einsatzbereit.  
  
 Beim Generieren eines DSN für einige ODBC\-Treibertypen ist der Pfad der tatsächlichen Datei erforderlich.  Wenn Sie beispielsweise einen Access\-DSN erstellen, müssen Sie den Pfad der MDB\-Datei kennen.  Außerdem sollten Sie über einen gültigen Benutzernamen und ein gültiges Kennwort verfügen.  So lautet der Systembenutzername für die meisten Access\-Systeme beispielsweise *admin*.  
  
 Beim Erstellen eines [Oracle](../../data/ado-rdo/oracle-connections.md)\-DSN sollten Sie die SQL\*Net\-Verbindungszeichenfolge kennen.  
  
## Siehe auch  
 [Erstellen von Datenbankverbindungen](../../data/ado-rdo/creating-database-connections.md)