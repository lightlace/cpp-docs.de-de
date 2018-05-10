---
title: Binäre Ausgabedateien | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- I/O [C++], binary output files
- files [C++], binary output files
- binary data, binary output files
ms.assetid: 180954af-8cd6-444b-9a76-2f630a3389d8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cdb101620b1a61f3a29057ee408cf9e89d38f9e8
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
---
# <a name="binary-output-files"></a>Binäre Ausgabedateien

Streams wurden ursprünglich für Text entwickelt, deswegen ist die Standardmethode für die Ausgabe „text“. Im Textmodus erweitert das neue Zeilenumbruchzeichen (hexadezimal 10) auf einen Zeilenumbruch (nur 16-Bit) aus. Die Erweiterung kann Probleme verursachen, wie hier gezeigt wird:

```cpp
// binary_output_files.cpp
// compile with: /EHsc
#include <fstream>
using namespace std;
int iarray[2] = { 99, 10 };
int main( )
{
    ofstream os( "test.dat" );
    os.write( (char *) iarray, sizeof( iarray ) );
}
```

Sie erwarten möglicherweise, dass dieses Programm die Bytesequenz { 99, 0, 10, 0 } ausgibt; stattdessen wird { 99, 0, 13, 10, 0 } ausgegeben, wodurch Probleme für ein Programm verursacht werden, das eine binäre Eingabe erwartet. Wenn sie eine echte binäre Ausgabe benötigen, in der die Zeichen nicht übersetzt geschrieben sind, können Sie die binäre Ausgabe mithilfe des openmode-Konstruktorarguments [ofstream](../standard-library/basic-ofstream-class.md#basic_ofstream) angeben:

```cpp
// binary_output_files2.cpp
// compile with: /EHsc
#include <fstream>
using namespace std;
int iarray[2] = { 99, 10 };

int main()
{
   ofstream ofs ( "test.dat", ios_base::binary );

   // Exactly 8 bytes written
   ofs.write( (char*)&iarray[0], sizeof(int)*2 );
}
```

## <a name="see-also"></a>Siehe auch

[Ausgabestreams](../standard-library/output-streams.md)<br/>
