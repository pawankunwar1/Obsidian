-> tool --> autorepeater


<mark style="background: #FFB8EBA6;">TIP 1</mark>
Setp 1: Find subdomanis 
Step 2 : FInd alive subdomains
Step 3: Run waybackurls in active subdomains 
Step 4 : After getting urls >> get active urls
Step 5: Search for keywords like:- `password, username, mail.com, token, access_token, url=, redirect_url, api_id, accessUrl, payment and other dorks use to find open redirects`
Step 6: Put burp collab server in the endpoint.
Step 7: To show more impact add port number at the end burp collab server domain --> it find out other services like SMTP also.

<mark style="background: #FFB8EBA6;">TIP 2</mark>
--> SSRF through Referer headers.
--> SSRF through X-Forwarded(or other header it use) Header
--> SSRF through Origin 

<mark style="background: #FFB8EBA6;">TIP 3</mark>
--> Maybe /admin cannot be access but /ADMIN , /Admin, /ADMin/ can access

<mark style="background: #FFB8EBA6;">TIP 4</mark>
Doogle dork --> inurl:http | inurl:proxy= | inurl:html= | inurl:data= | inurl:resource= inurl:& site:target[.]com

--> inurl:http | inurl:url= | inurl:path= | inurl:dest= | inurl:html= | inurl:data= | inurl:doman= | inurl:page= inurl:& site:example[.]com

<mark style="background: #FFF3A3A6;">TIP 5</mark>
-->bypassed a SSRF WAF by using a combination of IPV6 + Unicode. Payload for Metadata instances: http://[::ⓕⓕⓕⓕ:①⑥⑨。②⑤④。⑯⑨。②⑤④]:80

<mark style="background: #FF5582A6;">Tip 6</mark>
`cat subdomins.txt | httpx -silent -threads 1000 | gau | waybackurls | grep "=" | qsreplace burpcollaborator.net`

<mark style="background: #FF5582A6;">TIP 7</mark>
GET http://localhost:22 HTTP/1.1
Host: target 
Connection: close

<mark style="background: #FF5582A6;">TIp 8:-</mark>
here `_region=` parameter is vulnerable to SSRF because application take 
`_region` parameter value and do GET request likr GET `https://sns.region_paramtere_value.amazonaws.com`

--> PARAMETERS THAT ARE MOST LIKELY TO BE VULNERABLE TO SSRF
	1)dest  
    2) redirect  
     3)uri  
     4)path  
     5) continue  
      6)url  
     7)window  
    8)next  
   9)data  
   10)reference  
   11)site  
   12)html  
   13)val  
   14)validate  
   15)domain  
    16)callback  
   17)return  
    18)page  
   19)feed  
    20)host  
    21)port  
   22)to  
23)out  
   24)view  
   25)dir  
26)show  
27)navigation
    28) link
    29) return_url 
    30) target
    31) endpoint
    32) image_url
    33) proxy
    34) file
    35) api_url
    36) source
    37) fetch_url
    38) load
    39) remote_url
    40) content_url
    41) resource
    42) web_url
    43) navigate 
    44) site
    45) fetch_from
    46) fetch_target
    47) get_url
    48) external_url
    49) open_url
    50) link_target
    51) data_source
    52) request_url
    53) load_content
    54) web_fetch
    55) destination
    56) connect_to
    57) target_url
    58) load_from
    59) remote_resource
    60) external_resource
    61) remote_link
    62) fetch_location
    63) fetch_source
    64) fetch_domain
    65) access_point
    66) load_url
    67) fetch_address
    68) access_url
    69) retrive_from
    70) web_location
    71) destination_url
    72) web_location
    73) destination_url
    74) resource_url
    75) external_url
    76) request_source
    77) navigate_to
  78) request_target
79. **query_url**
80. **query_link**
81. **load_path**
82. **resource_path**
83. **access_address**
84. **nav_url**
85. **navigate_source**
86. **api_source**
87. **load_uri**
88. **load_resource**
89. **load_location**
90. **access_location**
91. **fetch_uri**
92. **fetch_path**
93. **data_path**
94. **external_path**
95. **site_path**
96. **content_source**
97. **query_resource**
98. **api_location**
99. **load_link**
100. **fetch_location**
101. destination_address
102. **remote_domain**
103. **target_location**
104. **external_address**
105. **load_source**
106. **fetch_domain**
107. **resource_location**
108. **web_resource**
109. **access_domain**
110. navigate_source
111. 111. **query_destination**
112. **retrieve_source**
113. **external_target**
114. **access_location**
115. **load_external**
116. **fetch_query**
117. **navigate_location**
118. **api_url**
119. **remote_resource**
120. **load_query**
121. **navigate_query**
122. **content_target**
123. **resource_query**
124. **access_query**
125. **fetch_target**
126. **data_query**
127. **external_data**
128. **navigate_data**
129. **web_data**
130. **site_query**
131. **api_data**
132. **content_data**
133. **resource_data**
134. **query_data**
135. **external_query**
136. **navigate_query**
137. **web_query**
138. **site_data**
139. **api_query**
140. **content_query**
141. **resource_query**
142. **query_target**
143. **external_target**
144. **navigate_target**
145. **web_target**
146. **site_target**
147. **api_target**
148. **content_target**
149. **resource_target**
150. **query_location**
151. **external_location**
152. **navigate_location**
153. **web_location**
154. **site_location**
155. **api_location**
156. **content_location**
157. **resource_location**
158. **query_uri**
159. **external_uri**
160. **navigate_uri**
161. **web_uri**
162. **site_uri**
163. **api_uri**
164. **content_uri**
165. **resource_uri**
166. **query_address**
167. **external_address**
168. **navigate_address**
169. **web_address**
170. **site_address**
171. **api_address**
172. **content_address**
173. **resource_address**
174. **query_path**
175. **external_path**
176. **navigate_path**
177. **web_path**
178. **site_path**
179. **api_path**
180. **content_path**
181. **resource_path**
182. **query_link**
183. **external_link**
184. **navigate_link**
185. **web_link**
186. **site_link**
187. **api_link**
188. **content_link**
189. **resource_link**
190. **query_source**
191. **external_source**
192. **navigate_source**
193. **web_source**
194. **site_source**
195. **api_source**
196. **content_source**
197. **resource_source**
198. **query_fetch**
199. **external_fetch**
200. navigate_fetch
201. 201. **resource_location**
202. **load_resource**
203. **fetch_destination**
204. **api_data_source**
205. **query_server**
206. **external_request**
207. **navigate_target**
208. **web_request**
209. **content_fetch**
210. **resource_query_url**
211. **query_remote_source**
212. **api_request_location**
213. **navigate_external_address**
214. **web_server_uri**
215. **site_data_path**
216. **access_query_uri**
217. **load_remote_content**
218. **query_content_url**
219. **external_data_location**
220. **navigate_request_path**
221. **api_source_uri**
222. **resource_external_uri**
223. **content_site_path**
224. **query_remote_location**
225. **external_request_uri**
226. **navigate_site_uri**
227. **web_data_source**
228. **site_request_location**
229. **access_api_location**
230. **load_target_address**
231. **query_external_path**
232. **external_fetch_url**
233. **navigate_data_source**
234. **api_server_path**
235. **resource_request_uri**
236. **content_query_location**
237. **query_site_source**
238. **navigate_data_uri**
239. **web_content_path**
240. **site_query_uri**
241. **access_data_source**
242. **load_server_uri**
243. **query_request_location**
244. **external_uri_path**
245. **navigate_target_location**
246. **api_content_uri**
247. **resource_fetch_path**
248. **content_server_uri**
249. **query_api_location**
250. **external_target_uri**
251. **navigate_site_address**
252. **web_external_source**
253. **site_data_uri**
254. **access_content_path**
255. **load_external_request**
256. **query_fetch_location**
257. **external_resource_uri**
258. **navigate_server_path**
259. **api_query_source**
260. **resource_site_uri**
261. **content_remote_path**
262. **query_server_location**
263. **external_api_address**
264. **navigate_content_url**
265. **web_fetch_source**
266. **site_request_uri**
267. **access_external_data**
268. **load_data_path**
269. **query_remote_uri**
270. **external_query_location**
271. **navigate_fetch_uri**
272. **api_query_url**
273. **resource_external_location**
274. **content_data_source**
275. **query_site_path**
276. **external_request_path**
277. **navigate_server_uri**
278. **web_remote_location**
279. **site_external_path**
280. **access_query_path**
281. **load_api_uri**
282. **query_data_location**
283. **external_remote_source**
284. **navigate_resource_path**
285. **api_content_path**
286. **resource_server_location**
287. **content_query_uri**
288. **query_data_source**
289. **navigate_api_uri**
290. **web_resource_uri**
291. **site_fetch_location**
292. **access_external_uri**
293. **load_query_source**
294. **query_content_source**
295. **external_data_uri**
296. **navigate_resource_uri**
297. **api_fetch_path**
298. **resource_server_uri**
299. **content_remote_uri**
300. **query_target_uri**
301. 301. **api_access_location**
302. **web_access_uri**
303. **site_fetch_path**
304. **external_access_data**
305. **load_fetch_source**
306. **query_fetch_uri**
307. **navigate_fetch_path**
308. **resource_query_uri**
309. **content_server_location**
310. **query_fetch_source**
311. **external_server_uri**
312. **navigate_resource_address**
313. **web_query_location**
314. **site_query_address**
315. **api_query_content**
316. **resource_site_path**
317. **content_remote_data**
318. **query_server_path**
319. **external_api_uri**
320. **navigate_data_address**
321. **web_access_path**
322. **site_remote_uri**
323. **access_query_source**
324. **load_target_uri**
325. **query_server_uri**
326. **external_remote_path**
327. **navigate_data_location**
328. **api_resource_location**
329. **resource_fetch_source**
330. **content_target_address**
331. **query_location_uri**
332. **external_data_source**
333. **navigate_server_source**
334. **web_server_location**
335. **site_data_address**
336. **access_query_location**
337. **load_uri_path**
338. **query_resource_uri**
339. **external_access_uri**
340. **navigate_query_path**
341. **api_content_address**
342. **resource_query_path**
343. **content_access_location**
344. **query_remote_address**
345. **external_site_uri**
346. **navigate_data_path**
347. **web_target_uri**
348. **site_server_location**
349. **access_api_uri**
350. **load_resource_source**
351. **query_location_address**
352. **external_access_location**
353. **navigate_server_uri**
354. **api_remote_uri**
355. **resource_data_source**
356. **content_fetch_uri**
357. **query_source_location**
358. **external_data_path**
359. **navigate_content_source**
360. **web_query_path**
361. **site_remote_address**
362. **access_server_uri**
363. **load_query_uri**
364. **query_access_path**
365. **external_resource_path**
366. **navigate_target_uri**
367. **api_fetch_location**
368. **resource_site_location**
369. **content_remote_location**
370. **query_target_address**
371. **external_server_source**
372. **navigate_site_data**
373. **web_location_uri**
374. **site_location_path**
375. **access_resource_uri**
376. **load_fetch_location**
377. **query_data_uri**
378. **external_query_source**
379. **navigate_fetch_source**
380. **api_fetch_uri**
381. **resource_query_location**
382. **content_server_address**
383. **query_location_path**
384. **external_target_source**
385. **navigate_server_data**
386. **web_query_source**
387. **site_location_uri**
388. **access_remote_path**
389. **load_query_location**
390. **query_data_address**
391. **external_fetch_source**
392. **navigate_target_path**
393. **api_fetch_address**
394. **resource_location_uri**
395. **content_data_uri**
396. **query_path_uri**
397. **external_server_uri**
398. **navigate_data_uri**
399. **web_resource_path**
400. **site_server_source**
401. **access_query_uri**
402. **load_remote_location**
403. **query_data_path**
404. **external_path_location**
405. **navigate_remote_uri**
406. **api_data_uri**
407. **resource_fetch_location**
408. **content_remote_path**
409. **query_location_uri**
410. **external_target_location**
411. **navigate_fetch_address**
412. **web_location_path**
413. **site_data_source**
414. **access_fetch_uri**
415. **load_server_path**
416. **query_remote_uri**
417. **external_uri_source**
418. **navigate_resource_uri**
419. **api_remote_source**
420. **resource_data_uri**
421. **content_server_uri**
422. **query_path_address**
423. **external_fetch_location**
424. **navigate_uri_path**
425. **web_path_uri**
426. **site_uri_location**
427. **access_path_source**
428. **load_query_address**
429. **query_source_path**
430. **external_location_uri**
431. **navigate_uri_source**
432. **api_path_uri**
433. **resource_address_location**
434. **content_fetch_path**
435. **query_remote_source**
436. **external_fetch_uri**
437. **navigate_server_address**
438. **web_access_location**
439. **site_fetch_uri**
440. **access_location_path**
441. **load_path_location**
442. **query_resource_source**
443. **external_data_location**
444. **navigate_source_path**
445. **api_location_address**
446. **resource_location_path**
447. **content_path_address**
448. **query_site_uri**
449. **external_location_path**
450. **navigate_uri_location**
451. **api_data_path**
452. **web_location_address**
453. **site_query_path**
454. **access_data_uri**
455. **load_server_path**
456. **query_remote_uri**
457. **external_uri_source**
458. **navigate_resource_uri**
459. **api_remote_source**
460. **resource_data_uri**
461. **content_server_uri**
462. **query_path_address**
463. **external_fetch_location**
464. **navigate_uri_path**
465. **web_path_uri**
466. **site_uri_location**
467. **access_path_source**
468. **load_query_address**
469. **query_source_path**
470. **external_location_uri**
471. **navigate_uri_source**
472. **api_path_uri**
473. **resource_address_location**
474. **content_fetch_path**
475. **query_remote_source**
476. **external_fetch_uri**
477. **navigate_server_address**
478. **web_access_location**
479. **site_fetch_uri**
480. **access_location_path**
481. **load_path_location**
482. **query_resource_source**
483. **external_data_location**
484. **navigate_source_path**
485. **api_location_address**
486. **resource_location_path**
487. **content_path_address**
488. **query_site_uri**
489. **external_location_path**
490. **navigate_uri_location**
491. **web_data_location**
492. **site_fetch_address**
493. **access_query_source**
494. **load_target_path**
495. **query_server_address**
496. **external_remote_source**
497. **navigate_data_path**
498. **api_resource_uri**
499. **resource_server_path**
500. **content_query_address**
501. **query_data_path**
502. **external_path_uri**
503. **navigate_remote_location**
504. **web_query_uri**
505. **site_path_location**
506. **access_resource_path**
507. **load_fetch_uri**
508. **query_location_source**
509. **external_query_uri**
510. **navigate_target_uri**
511. **api_query_location**
512. **resource_path_uri**
513. **content_external_source**
514. **query_data_uri**
515. **external_location_source**
516. **navigate_path_uri**
517. **web_uri_location**
518. **site_location_path**
519. **access_path_uri**
520. **load_location_path**
521. **query_resource_location**
522. **external_address_uri**
523. **navigate_uri_address**
524. **api_path_location**
525. **resource_query_address**
526. **content_query_path**
527. **query_server_source**
528. **external_data_uri**
529. **navigate_source_uri**
530. **web_path_location**
531. **site_uri_path**
532. **access_query_address**
533. **load_uri_location**
534. **query_location_uri**
535. **external_source_address**
536. **navigate_path_source**
537. **api_address_path**
538. **resource_location_uri**
539. **content_location_address**
540. **query_external_uri**
541. **external_source_path**
542. **navigate_address_uri**
543. **web_location_path**
544. **site_address_uri**
545. **access_path_location**
546. **load_data_uri**
547. **query_uri_path**
548. **external_path_address**
549. **navigate_resource_uri**
550. **api_location_location**
551. **resource_path_path**
552. **content_source_uri**
553. **query_server_path**
554. **external_uri_address**
555. **navigate_data_location**
556. **web_resource_address**
557. **site_data_uri**
558. **access_location_location**
559. **load_data_location**
560. **query_location_source**
561. **external_source_uri**
562. **navigate_address_path**
563. **api_data_location**
564. **resource_path_location**
565. **content_location_uri**
566. **query_server_address**
567. **external_location_path**
568. **navigate_uri_source**
569. **web_path_address**
570. **site_uri_location**
571. **access_path_source**
572. **load_query_address**
573. **query_source_location**
574. **external_location_uri**
575. **navigate_uri_path**
576. **api_path_address**
577. **resource_address_uri**
578. **content_uri_path**
579. **query_server_location**
580. **external_data_address**
581. **navigate_source_uri**
582. **web_query_path**
583. **site_location_uri**
584. **access_uri_source**
585. **load_location_address**
586. **query_resource_path**
587. **external_source_location**
588. **navigate_uri_address**
589. **api_path_source**
590. **resource_query_uri**
591. **content_address_location**
592. **query_server_uri**
593. **external_location_source**
594. **navigate_source_path**
595. **web_location_uri**
596. **site_path_address**
597. **access_uri_location**
598. **load_location_path**
599. **query_resource_location**
600. **external_address_uri
601. dir**
602. out
603. to 
604. port 
605. domain
606. dest


