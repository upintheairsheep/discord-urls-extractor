# discord-urls-extractor
Created for injesting URLs from DHT scrapes (and now discard2 ones, too!) into the Archiveteam URLs project.

Might not extract all URLs correctly. [#8](https://github.com/TheTechRobo/discordhistorytracker-urls-extractor/pull/8) improved on this, though.

## Usage with Discord History Tracker (DESKTOP APP ONLY)
Once you've got your .dht file, run:

    cargo r <file path> dht

Of course, if the file path has spaces, pad it with quotes (`"`).

Example: `cargo r /home/thetechrobo/Discordbackups/dsicord_data/SteamgridDB/SteamGridDB.dht dht`

## Usage with discard2
This one's a bit more work, because I'm too lazy to figure out the raw JSONL discard2 can output. If you don't know how to use a reader for discard2, check its README.

1. Use the `derive-urls` reader to get a list of attachments. Save that into a file. Do not name that file `urls.url` or `ignores.url`.
2. Use the `print` reader to output all messages as plain text. Save that into another file. Do not name that file `urls.url` or `ignores.url`.
3. Run `cargo r messages.txt plaintext`, assuming you named the file in Step 2 `messages.txt`.
4. Combine the file you saved in Step 1 with the `urls.url` file produced by this script.

Licenced under the Apache 2.0 licence. Copyright (C) TheTechRobo, 2021-2022.

>   Copyright 2021-2022 TheTechRobo
>
>   Licensed under the Apache License, Version 2.0 (the "License");
>   you may not use this file except in compliance with the License.
>   You may obtain a copy of the License at
>
>       http://www.apache.org/licenses/LICENSE-2.0
>
>   Unless required by applicable law or agreed to in writing, software
>   distributed under the License is distributed on an "AS IS" BASIS,
>   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
>   See the License for the specific language governing permissions and
>   limitations under the License.
