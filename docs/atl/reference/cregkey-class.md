---
title: "CRegKey Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CRegKey"
  - "ATL::CRegKey"
  - "ATL.CRegKey"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL, Registrierung"
  - "CRegKey class"
  - "Registrierung, Löschen von Schlüsseln"
  - "Registrierung, Löschen von Werten"
  - "Registrierung, Schreiben in"
ms.assetid: 3afce82b-ba2c-4c1a-8404-dc969e1af74b
caps.latest.revision: 25
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 28
---
# CRegKey Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse stellt Methoden zum Bearbeiten von Einträgen in der Systemregistrierung bereit.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen nicht verwendet werden, die in der Windows Runtime ausführen.  
  
## Syntax  
  
```  
  
class CRegKey  
  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CRegKey::CRegKey](../Topic/CRegKey::CRegKey.md)|Der \-Konstruktor.|  
|[CRegKey::~CRegKey](../Topic/CRegKey::~CRegKey.md)|Der Destruktor.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CRegKey::Attach](../Topic/CRegKey::Attach.md)|Rufen Sie diese Methode auf, um ein HKEY zum `CRegKey`\-Objekt anzufügen, indem Sie das [m\_hKey](../Topic/CRegKey::m_hKey.md)\-Memberhandle zu `hKey` festlegen.|  
|[CRegKey::Close](../Topic/CRegKey::Close.md)|Rufen Sie diese Methode auf, um das [m\_hKey](../Topic/CRegKey::m_hKey.md)\-Memberhandle freizugeben und es festzulegen, um auf NULL.|  
|[CRegKey::Create](../Topic/CRegKey::Create.md)|Rufen Sie diese Methode auf, um den angegebenen Schlüssel zu erstellen, wenn er nicht als Unterschlüssel von `hKeyParent` vorhanden ist.|  
|[CRegKey::DeleteSubKey](../Topic/CRegKey::DeleteSubKey.md)|Rufen Sie diese Methode auf, um den angegebenen Schlüssel aus der Registrierung zu entfernen.|  
|[CRegKey::DeleteValue](../Topic/CRegKey::DeleteValue.md)|Rufen Sie diese Methode auf, um ein Wertsfeld von [m\_hKey](../Topic/CRegKey::m_hKey.md) zu entfernen.|  
|[CRegKey::Detach](../Topic/CRegKey::Detach.md)|Rufen Sie diese Methode auf, um das [m\_hKey](../Topic/CRegKey::m_hKey.md)\-Memberhandle vom `CRegKey`\-Objekt und Menge `m_hKey` zu trennen zur NULL.|  
|[CRegKey::EnumKey](../Topic/CRegKey::EnumKey.md)|Rufen Sie diese Methode auf, um die Unterschlüssel des offenen Registrierungsschlüssels aufzulisten.|  
|[CRegKey::Flush](../Topic/CRegKey::Flush.md)|Rufen Sie diese Methode auf, um alle Attribute des geöffneten Registrierungsschlüssels in die Registrierung zu schreiben.|  
|[CRegKey::GetKeySecurity](../Topic/CRegKey::GetKeySecurity.md)|Rufen Sie diese Methode auf, um eine Kopie der Sicherheitsbeschreibung abzurufen, die den geöffneten Registrierungsschlüssel schützt.|  
|[CRegKey::NotifyChangeKeyValue](../Topic/CRegKey::NotifyChangeKeyValue.md)|Diese Methode benachrichtigt den Aufrufer über Änderungen an den Attributen oder am Inhalt des offenen Registrierungsschlüssels.|  
|[CRegKey::Open](../Topic/CRegKey::Open.md)|Rufen Sie diese Methode auf, um den angegebenen Schlüssel und Festlegen [m\_hKey](../Topic/CRegKey::m_hKey.md) in Anspruch dieser Schlüssel zu öffnen.|  
|[CRegKey::QueryBinaryValue](../Topic/CRegKey::QueryBinaryValue.md)|Rufen Sie diese Methode auf, um die Binärdaten für einen bestimmten Wertnamen abzurufen.|  
|[CRegKey::QueryDWORDValue](../Topic/CRegKey::QueryDWORDValue.md)|Rufen Sie diese Methode auf, um die DWORD\-Daten für einen angegebenen Wertnamen abzurufen.|  
|[CRegKey::QueryGUIDValue](../Topic/CRegKey::QueryGUIDValue.md)|Rufen Sie diese Methode auf, um die GUIDdaten für einen angegebenen Wertnamen abzurufen.|  
|[CRegKey::QueryMultiStringValue](../Topic/CRegKey::QueryMultiStringValue.md)|Rufen Sie diese Methode auf, um die Daten der mehrteiligen Zeichenfolge für einen angegebenen Wertnamen abzurufen.|  
|[CRegKey::QueryQWORDValue](../Topic/CRegKey::QueryQWORDValue.md)|Rufen Sie diese Methode auf, um die QWORDdaten für einen angegebenen Wertnamen abzurufen.|  
|[CRegKey::QueryStringValue](../Topic/CRegKey::QueryStringValue.md)|Rufen Sie diese Methode auf, um die Zeichenfolgendaten für einen angegebenen Wertnamen abzurufen.|  
|[CRegKey::QueryValue](../Topic/CRegKey::QueryValue.md)|Rufen Sie diese Methode auf, um die Daten für das angegebene Wertsfeld von [m\_hKey](../Topic/CRegKey::m_hKey.md) abzurufen.  Frühere Versionen dieser Methode werden nicht mehr unterstützt und werden als **ATL\_DEPRECATED** markiert.|  
|[CRegKey::RecurseDeleteKey](../Topic/CRegKey::RecurseDeleteKey.md)|Rufen Sie diese Methode auf, um den angegebenen Schlüssel aus der Registrierung zu entfernen und alle Unterschlüssel explizit zu entfernen.|  
|[CRegKey::SetBinaryValue](../Topic/CRegKey::SetBinaryValue.md)|Rufen Sie diese Methode auf, um den Binärwert des Registrierungsschlüssels festzulegen.|  
|[CRegKey::SetDWORDValue](../Topic/CRegKey::SetDWORDValue.md)|Rufen Sie diese Methode auf, um den DWORD\-Wert des Registrierungsschlüssels festzulegen.|  
|[CRegKey::SetGUIDValue](../Topic/CRegKey::SetGUIDValue.md)|Rufen Sie diese Methode auf, um den GUID\-Wert des Registrierungsschlüssels festzulegen.|  
|[CRegKey::SetKeySecurity](../Topic/CRegKey::SetKeySecurity.md)|Rufen Sie diese Methode auf, um die Sicherheit des Registrierungsschlüssels festzulegen.|  
|[CRegKey::SetKeyValue](../Topic/CRegKey::SetKeyValue.md)|Rufen Sie diese Methode auf, um Daten auf einem angegebenen Wertsgebiet eines angegebenen Schlüssels zu speichern.|  
|[CRegKey::SetMultiStringValue](../Topic/CRegKey::SetMultiStringValue.md)|Rufen Sie diese Methode auf, um den Wert der mehrteiligen Zeichenfolge des Registrierungsschlüssels festzulegen.|  
|[CRegKey::SetQWORDValue](../Topic/CRegKey::SetQWORDValue.md)|Rufen Sie diese Methode auf, um den QWORDwert des Registrierungsschlüssels festzulegen.|  
|[CRegKey::SetStringValue](../Topic/CRegKey::SetStringValue.md)|Rufen Sie diese Methode auf, um den Zeichenfolgenwert des Registrierungsschlüssels festzulegen.|  
|[CRegKey::SetValue](../Topic/CRegKey::SetValue.md)|Rufen Sie diese Methode auf, um Daten auf dem angegebenen Wertsgebiet von [m\_hKey](../Topic/CRegKey::m_hKey.md) zu speichern.  Frühere Versionen dieser Methode werden nicht mehr unterstützt und werden als **ATL\_DEPRECATED** markiert.|  
  
### Öffentliche Operatoren  
  
|Name|Description|  
|----------|-----------------|  
|[CRegKey::operator HKEY](../Topic/CRegKey::operator%20HKEY.md)|Konvertiert ein Objekt `CRegKey` zu einem HKEY.|  
|[CRegKey::operator \=](../Topic/CRegKey::operator%20=.md)|Zuweisungsoperator|  
  
### Öffentliche Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[CRegKey::m\_hKey](../Topic/CRegKey::m_hKey.md)|Enthält ein Handle des Registrierungsschlüssels, der mit dem `CRegKey`\-Objekt zugeordnet ist.|  
|[CRegKey::m\_pTM](../Topic/CRegKey::m_pTM.md)|Zeiger auf `CAtlTransactionManager`\-Objekt|  
  
## Hinweise  
 `CRegKey` stellt Methoden zum Erstellen und Löschen von Schlüsseln und von Werten in der Systemregistrierung bereit.  Die Registrierung enthält ein Installationbesonderen, das von den Definitionen für Systemkomponenten, wie Softwareversionszahlen, Logisch\-zusystemtest Zuordnungen der installierten Hardware und COM\-Objekte festgelegt ist.  
  
 `CRegKey` stellt eine Programmierschnittstelle für die Systemregistrierung für einen angegebenen Computer bereit.  Beispielsweise einen bestimmten Registrierungsschlüssel öffnen, Aufruf `CRegKey::Open`.  So fügen Sie einen Datenwert, einen Aufruf `CRegKey::QueryValue` oder `CRegKey::SetValue` abrufen oder ändern, bzw.  Um eine Schlüssel zu schließen, rufen Sie `CRegKey::Close` auf.  
  
 Wenn Sie einen Schlüssel schließen, werden die Registrierungsdaten auf die Festplatte geschrieben \(geleert\).  Dieser Prozess erfordert möglicherweise einige Sekunden.  Wenn die Anwendung Registrierungsdaten explizit auf die Festplatte schreiben muss, können Sie die Funktion [RegFlushKey](http://msdn.microsoft.com/library/windows/desktop/ms724867) Win32 aufrufen.  verwendet jedoch **RegFlushKey** viele Systemressourcen und sollte nur aufgerufen werden, wenn es unbedingt erforderlich ist.  
  
> [!IMPORTANT]
>  Alle Methoden, die dem Aufrufer ermöglichen, einen Registrierungsspeicherort anzugeben, haben die Möglichkeit, Daten zu lesen, die nicht vertrauenswürdig sind.  Methoden, die [RegQueryValueEx](http://msdn.microsoft.com/library/windows/desktop/ms724911) verwendet wird, sollten in Erwägung ziehen, dass diese Funktion nicht explizit Zeichenfolgen behandelt, die beendet NULL sind.  Beide Bedingungen sollten für durch den Aufrufcode überprüft werden.  
  
## Anforderungen  
 **Header:**  atlbase.h  
  
## Siehe auch  
 [Beispiel für DCOM](../../top/visual-cpp-samples.md)   
 [Class Overview](../../atl/atl-class-overview.md)   
 [Registry Overview](http://msdn.microsoft.com/library/windows/desktop/ms724871)   
 [Registry Functions](http://msdn.microsoft.com/library/windows/desktop/ms724875)   
 [Registry Value Types](http://msdn.microsoft.com/library/windows/desktop/ms724884)