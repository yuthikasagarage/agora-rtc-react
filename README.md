#  React Wrapper for Agora RTC SDK

A react (react.js) wrapper for [Agora RTC NG SDK](https://www.npmjs.com/package/agora-rtc-sdk-ng).

This wrapper supports **React >= v16.8**

## Install
```bash
npm install git://github.com/AgoraIO-Community/agora-rtc-react#v1.1.0
```

## Usage
```tsx
import React from "react";
import { AgoraVideoPlayer, createClient, createMicrophoneAndCameraTracks } from "agora-rtc-react";

const config = {mode: "rtc", codec: "vp8"}

const useClient = createClient(config);
const useMicrophoneAndCameraTracks = createMicrophoneAndCameraTracks();

const App = () => {
  const client = useClient();
  const { ready, tracks } = useMicrophoneAndCameraTracks();

  return (
    ready && <AgoraVideoPlayer videoTrack={tracks[1]} style={{height: '100%', width: '100%'}} />
  )
}
......
