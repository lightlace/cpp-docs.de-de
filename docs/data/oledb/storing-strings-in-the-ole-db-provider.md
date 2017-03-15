---
title: "Speichern von Zeichenfolgen im OLE&#160;DB-Anbieter | Microsoft Docs"
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
  - "Benutzerdatensätze, Bearbeiten"
ms.assetid: 36cb9635-067c-4cad-8f85-962f28026f6a
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Speichern von Zeichenfolgen im OLE&#160;DB-Anbieter
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Der ATL\-OLE DB\-Anbieter\-Assistent erstellt in der Datei MyProviderRS.h einen Standardbenutzerdatensatz mit dem Namen `CWindowsFile`.  Um die beiden Zeichenfolgen zu verarbeiten, ändern Sie entweder `CWindowsFile` oder fügen, wie im folgenden Code dargestellt, einen eigenen Benutzerdatensatz hinzu:  
  
```  
////////////////////////////////////////////////////////////////////////  
class CAgentMan:   
   public WIN32_FIND_DATA  
   DWORD dwBookmark;              // Add this  
   TCHAR szCommand[256];          // Add this  
   TCHAR szText[256];             // Add this  
   TCHAR szCommand2[256];         // Add this  
   TCHAR szText2[256];            // Add this  
  
{  
public:  
BEGIN_PROVIDER_COLUMN_MAP()  
   PROVIDER_COLUMN_ENTRY_STR(OLESTR("Command"), 1, 256, GUID_NULL, CAgentMan, szCommand)  
   PROVIDER_COLUMN_ENTRY_STR(OLESTR("Text"), 2, 256, GUID_NULL, CAgentMan, szText)   
   PROVIDER_COLUMN_ENTRY_STR(OLESTR("Command2"), 3, 256, GUID_NULL, CAgentMan, szCommand2)  
   PROVIDER_COLUMN_ENTRY_STR(OLESTR("Text2"),4, 256, GUID_NULL, CAgentMan, szText2)  
END_PROVIDER_COLUMN_MAP()  
   bool operator==(const CAgentMan& am) // This is optional   
   {  
      return (lstrcmpi(cFileName, wf.cFileName) == 0);  
   }  
};  
```  
  
 Die Datenmember `szCommand` und `szText` stehen für die beiden Zeichenfolgen, wobei `szCommand2` und `szText2` ggf. zusätzliche Spalten bereitstellen.  Der `dwBookmark`\-Datenmember wird für diesen einfachen schreibgeschützten Anbieter nicht benötigt, er wird jedoch später zum Hinzufügen einer `IRowsetLocate`\-Schnittstelle verwendet, siehe [Erweitern des einfachen schreibgeschützten Anbieters](../../data/oledb/enhancing-the-simple-read-only-provider.md).  Der Operator "`==`" wird zum Vergleichen von Instanzen verwendet \(er kann optional implementiert werden\).  
  
 Anschließend sollte der Anbieter bereit für die Kompilierung und Ausführung sein.  Um den Anbieter zu testen, benötigen Sie einen Consumer mit übereinstimmenden Funktionen.  Unter [Implementieren eines einfachen Consumers](../../data/oledb/implementing-a-simple-consumer.md) erfahren Sie, wie Sie einen solchen Testconsumer erstellen.  Führen Sie den Testconsumer mit dem Anbieter aus.  Stellen Sie sicher, dass der Testconsumer die richtigen Zeichenfolgen vom Anbieter abruft, wenn Sie im Dialogfeld **Testconsumer** auf **Ausführen** klicken.  
  
 Wenn Sie den Anbieter erfolgreich getestet haben, können Sie seinen Funktionsumfang durch die Implementierung zusätzlicher Schnittstellen erweitern.  Unter [Erweitern des einfachen schreibgeschützten Anbieters](../../data/oledb/enhancing-the-simple-read-only-provider.md) finden Sie ein Beispiel dazu.  
  
## Siehe auch  
 [Implementieren des einfachen schreibgeschützten Anbieters](../../data/oledb/implementing-the-simple-read-only-provider.md)