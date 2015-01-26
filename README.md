# aamva-plugin.js

small jquery plugin that helps to parse magnetic stripe from aamva


## Usage

```javascript
  var stripe_data = '%FLDELRAY BEACH^DOE$JOHN$^4818 S FEDERAL BLVD^           \?\
  ;6360100462172082009=2101198299090=?\
  #! 33435      I               1600                                   ECCECC00000?';

  var res = $.aamva.parse($stripe_data);

  console.log("DMV ID:",res.id());
  console.log("First name:",res.name().first);
  console.log("Last name:",res.name().last);
  console.log("Middle name:",res.name().middle);
  console.log("Sex:",res.sex()); /* MALE, FEMALE, MISSING/INVALID */
  console.log("Entire object", res);
  console.log("DOB:",res.birthday()); /* Thu Jan 08 1987 00:00:00 GMT-0500 (EST) */

/* 
  output: 
        { state: 'FL',
          city: 'DELRAY BEACH',
          name: [Function],
          address: '4818 S FEDERAL BLVD',
          iso_iin: '636010',
          dl: '0462172082009',
          expiration_date: '2101',
          birthday: [Function],
          dl_overflow: '0',
          cds_version: '#',
          jurisdiction_version: '!',
          postal_code: '33435      ',
          class: 'I ',
          restrictions: '          ',
          endorsments: '    ',
          sex: [Function],
          height: '600',
          weight: '   ',
          hair_color: '   ',
          eye_color: '   ',
          misc: '                          ECCECC00000',
          id: [Function] }
*/

```

## Contributing

If you find a bug or willing to add some enhancement, pull requests are very welcome

## Release History

* 0.0.1 Initial release

## Legal

This program is free software; you can redistribute it and/or
modify it under the terms of the GNU General Public License
as published by the Free Software Foundation; either version 2
of the License, or (at your option) any later version.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU General Public License for more details.

You should have received a copy of the GNU General Public License
along with this program; if not, write to the Free Software
Foundation, Inc., 51 Franklin Street, Fifth Floor, Boston, MA  02110-1301, USA.
