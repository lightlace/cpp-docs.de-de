---
title: "Platform::COMException-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::COMException"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::COMException-Klasse"
ms.assetid: 44fda4e5-574f-4d12-ab5f-4ff3f277448d
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 4
---
# Platform::COMException-Klasse
Stellt COM\-Fehler dar, die beim Ausführen einer Anwendung auftreten. COMException ist die Basisklasse für einen Satz vordefinierter Standardausnahmen.  
  
## Syntax  
  
```cpp  
public ref class COMException : Exception,    IException,    IPrintable,    IEquatable  
```  
  
## Mitglieder  
 Die COMException\-Klasse erbt von der Object\-Klasse und den Schnittstellen IException, IPrintable und IEquatable.  
  
 COMException verfügt auch über die folgenden Membertypen.  
  
 **Konstruktoren**  
  
|Member|Beschreibung|  
|------------|------------------|  
|`COMException`|Initialisiert eine neue Instanz der COMException\-Klasse.|  
  
 **Methoden**  
  
 Die COMException\-Klasse erbt die Methoden Equals\(\), Finalize\(\), GetHashCode\(\), GetType\(\), MemberwiseClose\(\) und ToString\(\) von der [Platform::Object\-Klasse](../cppcx/platform-object-class.md).  
  
 **Eigenschaften**  
  
 Die COMException\-Klasse verfügt auch über die folgenden Eigenschaften.  
  
|Member|Beschreibung|  
|------------|------------------|  
|[Exception::HResult\-Eigenschaft](../cppcx/exception-hresult-property.md)|Das HRESULT, das der Ausnahme entspricht.|  
|[Exception::Message\-Eigenschaft](../cppcx/exception-message-property.md)|Meldung, in der die Ausnahme beschrieben wird.|  
  
## Abgeleitete Ausnahmen  
 Die folgenden vordefinierten Ausnahmen werden von COMException abgeleitet. Sie unterscheiden sich von COMException nur im Namen, im Namen des Konstruktors und dem zugrunde liegenden HRESULT\-Wert.  
  
|Name|Zugrunde liegendes HRESULT|Beschreibung|  
|----------|--------------------------------|------------------|  
|COMException|*Benutzerdefiniertes HRESULT*|Wird ausgelöst, wenn ein COM\-Methodenaufruf ein unbekanntes HRESULT zurückgibt.|  
|AccessDeniedException|E\_ACCESSDENIED|Wird ausgelöst, wenn der Zugriff auf eine Ressource oder eine Funktion verweigert wird.|  
|ChangedStateException|E\_CHANGED\_STATE|Wird ausgelöst, wenn Methoden eines Auflistungsiterators oder einer Auflistungsansicht aufgerufen werden, nachdem die übergeordnete Auflistung geändert wurde. Hierdurch werden die Ergebnisse der Methode ungültig.|  
|ClassNotRegisteredException|REGDB\_E\_CLASSNOTREG|Wird ausgelöst, wenn eine COM\-Klasse nicht registriert wurde.|  
|DisconnectedException|RPC\_E\_DISCONNECTED|Wird ausgelöst, wenn ein Objekt von den Clients getrennt wurde.|  
|FailureException|E\_FAIL|Wird ausgelöst, wenn ein Vorgang fehlschlägt.|  
|InvalidArgumentException|E\_INVALIDARG|Wird ausgelöst, wenn eines der Argumente für eine Methode ungültig ist.|  
|InvalidCastException|E\_NOINTERFACE|Wird ausgelöst, wenn ein Typ nicht in einen anderen Typ umgewandelt werden kann.|  
|NotImplementedException|E\_NOTIMPL|Wird ausgelöst, wenn eine Schnittstellenmethode nicht bei der Klasse implementiert wurde.|  
|NullReferenceException|E\_POINTER|Wird ausgelöst, wenn der Versuch gemacht wird, einen Verweis auf ein NULL\-Objekt zu dereferenzieren.|  
|OperationCanceledException|E\_ABORT|Wird nach dem Abbrechen eines Vorgangs ausgelöst.|  
|OutOfBoundsException|E\_BOUNDS|Wird ausgelöst, wenn ein Vorgang versucht, auf Daten außerhalb des gültigen Bereichs zuzugreifen.|  
|OutOfMemoryException|E\_OUTOFMEMORY|Wird ausgelöst, wenn nicht genügend Arbeitsspeicher vorhanden ist, um den Vorgang abzuschließen.|  
  
## Anforderungen  
 **Unterstützter Client \(Min.\):** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **Unterstützter Server \(Min.\):** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **Namespace:** Platform  
  
 **Metadaten:** platform.winmd  
  
## Siehe auch  
 [Plattformnamespace](../cppcx/platform-namespace-c-cx.md)