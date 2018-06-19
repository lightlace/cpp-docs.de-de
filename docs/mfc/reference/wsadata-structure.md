---
title: WSADATA-Struktur | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- WSADATA
dev_langs:
- C++
helpviewer_keywords:
- WSADATA structure [MFC]
ms.assetid: 80cc60e5-f9ae-4290-8ed5-07003136627d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 93c98f792e1d72d3e6d4a8e15b8347c653b32f46
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33380083"
---
# <a name="wsadata-structure"></a>WSADATA-Struktur
Die `WSADATA` Struktur dient zum Speichern von Initialisierungsinformationen für die Windows-Sockets zurückgegeben, die durch einen Aufruf der `AfxSocketInit` globale Funktion.  
  
## <a name="syntax"></a>Syntax  
  
```  
struct WSAData {  
    WORD wVersion;  
    WORD wHighVersion;  
    char szDescription[WSADESCRIPTION_LEN+1];  
    char szSystemStatus[WSASYSSTATUS_LEN+1];  
    unsigned short iMaxSockets;  
    unsigned short iMaxUdpDg;  
    char FAR* lpVendorInfo;  
};  
```  
  
#### <a name="parameters"></a>Parameter  
 *wVersion*  
 Die Version der Windows Sockets-Spezifikation, die die Windows-Sockets-DLL den Aufrufer erwartet.  
  
 *wHighVersion*  
 Die höchste Version der Windows Sockets-Spezifikation, die diese DLL unterstützen kann (wie oben beschrieben ebenfalls codiert). In der Regel wird dies entspricht dem **wVersion**.  
  
 *szDescription*  
 Eine Null-terminierte ASCII-Zeichenfolge in die Windows-Sockets-DLL eine Beschreibung der Windows Sockets-Implementierung, einschließlich Hersteller-ID kopiert. Der Text (bis zu 256 Zeichen lang) kann alle Zeichen enthalten, aber Lieferanten sind cautioned gegen einschließlich Steuerelements und Formatieren von Zeichen: die am wahrscheinlichsten Verwendung, die eine Anwendung dies gestellt wird, ist zum Anzeigen dieser (möglicherweise abgeschnitten) in eine Statusmeldung.  
  
 *szSystemStatus*  
 Eine Null-terminierte ASCII-Zeichenfolge in die Windows Sockets-DLL relevante Status oder Konfiguration Informationen kopiert. Windows Sockets-DLL sollte dieses Feld verwenden, nur, wenn die Informationen kann nützlich sein, um den Benutzer oder Supportpersonal; Es sollte nicht als eine Erweiterung der berücksichtigt werden die **SzDescription** Feld.  
  
 *iMaxSockets*  
 Die maximale Anzahl von Sockets, die ein einzelnen Prozess potenziell öffnen können. Windows Sockets-Implementierung bieten einen globalen Pool von Sockets für die Zuordnung zu einem Prozess; Alternativ können sie Ressourcen pro Prozess für Sockets zugewiesen werden. Die Anzahl reflektiert auch die Möglichkeit, in der die Windows-Sockets-DLL oder der Clientnetzwerksoftware konfiguriert wurde. Anwendungsentwickler können anhand dieser Zahl als einfach gehalten Angabe der gibt an, ob die Windows-Sockets-Implementierung von der Anwendung verwendet werden kann. Z. B. X Windows-Server überprüfen **iMaxSockets** beim ersten Start: Wenn es weniger als 8 ist, würde die Anwendung eine Fehlermeldung Informieren der Benutzer die Clientnetzwerksoftware neu konfigurieren angezeigt. (Dies ist eine Situation, in der die **SzSystemStatus** Text verwendet werden kann.) Selbstverständlich besteht keine Garantie, die eine bestimmte Anwendung tatsächlich zuordnen können **iMaxSockets** sockets, da andere Windows-Sockets-Anwendungen verwendet werden können.  
  
 *iMaxUdpDg*  
 Die Größe in Bytes des größten Datagramms, User Datagram Protocol (UDP), die gesendet oder von einer Windows-Sockets-Anwendung empfangen werden können. Wenn die Implementierung keine Beschränkung erzwingt **iMaxUdpDg** 0 (null). In den verschiedensten Implementierungen dieses Berkeley-Sockets ist eine implizite kann maximal 8192 Bytes auf UDP-Datagramme (die ggf. fragmentiert sind). Windows Sockets-Implementierung können Sie eine Grenze basieren, z. B. auf die Zuordnung von Fragment Reassemblierung Puffer festlegen. Der Minimalwert der **iMaxUdpDg** für eine kompatible Windows Sockets-Implementierung ist 512. Beachten Sie, dass unabhängig vom Wert der **iMaxUdpDg**, es wird davon abgeraten, bei dem Versuch, einen broadcast Datagramm gesendet werden, die größer als das Maximum Transmission Unit (MTU) für das Netzwerk ist. (Der Windows Sockets-API bietet einen Mechanismus, um die maximale Übertragungseinheit zu ermitteln, aber muss nicht weniger als 512 Byte sein.)  
  
 *lpVendorInfo*  
 Ein ferner Zeiger auf eine Struktur herstellerspezifische Daten. Die Definition dieser Struktur (falls angegeben) ist Bestandteil der Windows Sockets-Spezifikation.  
  
> [!NOTE]
>  In MFC können die `WSADATA` Struktur wird zurückgegeben, durch die `AfxSocketInit` -Funktion, die Sie in Aufrufen Ihrer `InitInstance` Funktion. Sie können die Struktur abrufen und im Programm zu speichern, wenn Sie Informationen aus einem späteren Zeitpunkt verwenden müssen.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** winsock2.h  
  
## <a name="see-also"></a>Siehe auch  
 [Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit)

