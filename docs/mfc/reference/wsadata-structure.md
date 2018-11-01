---
title: WSADATA-Struktur
ms.date: 11/04/2016
f1_keywords:
- WSADATA
helpviewer_keywords:
- WSADATA structure [MFC]
ms.assetid: 80cc60e5-f9ae-4290-8ed5-07003136627d
ms.openlocfilehash: 06e8423a00ecfe5179dbfe3e03f61dbf1ef870b3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50474021"
---
# <a name="wsadata-structure"></a>WSADATA-Struktur

Die `WSADATA` Struktur dient zum Speichern von Windows Sockets-Initialisierungsinformationen zurückgegeben, die durch einen Aufruf der `AfxSocketInit` globale Funktion.

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

*wVersion*<br/>
Die Version der Windows Sockets-Spezifikation, die die Windows Sockets-DLL den Aufrufer erwartet.

*wHighVersion*<br/>
Die höchste Version der Windows Sockets-Spezifikation, die diese DLL-Datei unterstützen (wie oben beschrieben auch codiert). Normalerweise ist dies entspricht dem *wVersion*.

*szDescription*<br/>
Eine Null-terminierte ASCII-Zeichenfolge in der die Windows Sockets-DLL eine Beschreibung der Windows Sockets-Implementierung, einschließlich Hersteller-ID kopiert. Der Text (bis zu 256 Zeichen lang) kann beliebige Zeichen enthalten, aber Anbietern einschließlich-Steuerelements und Formatieren von Zeichen hingewiesen werden: die am wahrscheinlichsten Verwendung, die eine Anwendung dies eingefügt wird, wird angezeigt (möglicherweise gekürzt) in eine Statusmeldung.

*szSystemStatus*<br/>
Eine Null-terminierte ASCII-Zeichenfolge in der die Windows Sockets-DLL relevante Informationen ein Status oder Konfiguration kopiert. Die Windows Sockets-DLL sollte dieses Feld verwenden, nur, wenn die Informationen kann hilfreich sein, den Benutzer oder Supportpersonal; Es sollte nicht als eine Erweiterung der betrachtet die *SzDescription* Feld.

*iMaxSockets*<br/>
Die maximale Anzahl von Sockets, die ein einzelnen Prozess möglicherweise öffnen können. Eine Windows Sockets-Implementierung bietet einen globalen Pool von Sockets für die Zuordnung zu einem beliebigen Prozess; Alternativ können sie pro-Prozess-Ressourcen für Sockets zuordnen. Die Anzahl kann auch die Art wider, in der die Windows Sockets-DLL oder der Clientnetzwerksoftware konfiguriert wurde. Anwendungsentwickler können diese Zahl als Angabe, ob die Windows Sockets-Implementierung verwendet werden, von der Anwendung ist einfach gehalten. Ein X-Windows-Server möglicherweise sehen Sie z. B. *iMaxSockets* beim ersten Start: Wenn es kleiner als 8 ist, würde die Anwendung eine Fehlermeldung angezeigt, den Benutzer anweisen, zum Konfigurieren der Clientnetzwerksoftware angezeigt. (Dies ist eine Situation, in dem die *SzSystemStatus* Text verwendet werden kann.) Offensichtlich besteht keine Garantie, die eine bestimmte Anwendung tatsächlich zuordnen können *iMaxSockets* sockets, weil andere Windows Sockets-Anwendungen verwendet werden kann.

*iMaxUdpDg*<br/>
Die Größe in Bytes des größten Datagramms User Datagram Protocol (UDP), die gesendet oder von einer Windows-Sockets-Anwendung empfangen werden können. Wenn die Implementierung keine Beschränkung, erzwingt *iMaxUdpDg* ist 0 (null). In vielen Implementierungen der Berkeley-Sockets gibt es eine implizite Beschränkung der 8192 Bytes auf UDP-Datagramme (die ggf. fragmentiert sind). Eine Windows Sockets-Implementierung kann gilt einen Grenzwert basierend, z. B. über die Zuordnung von Fragment objekteinkapselung Puffer festlegen. Der minimale Wert der *iMaxUdpDg* für eine konforme Windows Sockets-Implementierung ist 512. Beachten Sie, dass unabhängig vom Wert der *iMaxUdpDg*, es wird davon abgeraten, die versuchen, ein broadcast-Datagramm zu senden, die größer als das Maximum Transmission Unit (MTU) für das Netzwerk ist. (Der Windows Sockets-API bietet einen Mechanismus, um die MTU erkennen nicht, aber er muss nicht weniger als 512 Byte sein.)

*lpVendorInfo*<br/>
Ein weit Zeiger auf eine Struktur herstellerspezifischen Daten. Die Definition dieser Struktur (falls angegeben) ist über den Rahmen der Windows Sockets-Spezifikation hinaus.

> [!NOTE]
>  In MFC können die `WSADATA` Struktur wird zurückgegeben, durch die `AfxSocketInit` -Funktion, die Sie in Aufrufen Ihrer `InitInstance` Funktion. Sie können die Struktur abrufen und in Ihrem Programm zu speichern, wenn Sie die Informationen später verwenden möchten.

## <a name="requirements"></a>Anforderungen

**Header:** winsock2.h

## <a name="see-also"></a>Siehe auch

[Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit)

