! ––––––––––––––––––––––––––––––––––––––––––––––––––––––––––––––––––––––––––––––––––––––––––––
! Blocking Keywords

! Option 1a – Separate Rules for Single Keywords
! To block any URL containing your keyword, use the rule: ||*keyword*^
! ||*porn*^
! ||*ads*^
! ||*gambling*^
! ||*keyword*^ matches anywhere in the full URL (domain, path, query, or file name).
! Each line is a separate rule. This rule syntax is readable & widely compatible. 

! Option 1b – Separate Rules for Consecutive Keywords
! To block any URL that contains consecutive keywords, insert * between each keyword
! ||*celebrity*list*^ –  example.com/celebrity-list, example.com/top-celebrity/list-of-stars, example.com/articles/celebrity_listicle.html, cdn.example.com/celebrityTop10List.jpg
! The * matches any number of any characters, including spaces, hyphens, underscores, slashes, numbers, or letters.

! Option 2 – Domain Specific Match for Multiple Keywords
! To block any URL on example.com that contains your keyword(s), use the rule: ||example.com/*keyword*
! ||example.com/*porn*
! ||example.com/*ads*
! ||example.com/*gambling*
! Each line is a separate rule. 

! Option 3 – Use a Single RegEx Rule
! If you prefer a single advanced & compact RegEx rule to match multiple keywords in URLs, use: /^https?:\/\/.*(porn|ads|gambling).*$/
! RegEx must start and end with /.../, and you can append $important to ensure the block takes precedence, ex: /^https?:\/\/.(porn|ads|gambling).*$/\$important
! Avoid overusing RegEx rules, as they are slower and may cause performance issues if you use many. Only use them in desktop versions of AdGuard.

! Notes:
! Use ^ to anchor the end of a domain or path section.
! Use wildcards * to broaden matches but avoid over-blocking.
! These rules block URLs, not page content (e.g., if “keyword” appears in visible text, it won’t be blocked).

! ––––––––––––––––––––––––––––––––––––––––––––––––––––––––––––––––––––––––––––––––––––––––––––
! Blocking TLDs-cc

! To block ALL domains (e.g., example.ru, abc.ru) under a specific ccTLD, use: ||*.ru^
! Be cautious when blocking entire ccTLDs, because you may unintentionally block legitimate services. 

! To unblock ALL domains under a specific ccTLD, use: @@||*.ch^
! To unblock specific domains under a blocked ccTLD, use: @@||trustedsite.ch^, @@||example.ch^, @@||secure.ch^

! Syntax Explanation:
! || — wildcard for any domain.
! *. — matches all subdomains and domains.
! ru — the ccTLD you want to block.
! ^ — marks the end of the domain part.

! ––––––––––––––––––––––––––––––––––––––––––––––––––––––––––––––––––––––––––––––––––––––––––––
! Blocking TLDs-g

! To block ALL domains (e.g., example.aaa, abc.aaa) under a specific gTLD, use: ||*.aaa^
! Be cautious when blocking entire gTLDs, because you may unintentionally block legitimate services. 

! To unblock ALL domains under a specific gTLD, use: @@||*.abb^
! To unblock specific domains under a blocked gTLD, use: @@||trustedsite.abb^, @@||example.abb^, @@||secure.abb^

! Syntax Explanation:
! || — wildcard for any domain.
! *. — matches all subdomains and domains.
! aaa — the gTLD you want to block.
! ^ — marks the end of the domain part.
