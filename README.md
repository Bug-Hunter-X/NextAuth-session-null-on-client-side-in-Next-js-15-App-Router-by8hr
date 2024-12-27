# NextAuth session null on client-side in Next.js 15 App Router

This repository demonstrates a bug where the NextAuth session is not available on the client-side when using the Next.js 15 App Router. The `session` object is always null, even after successful authentication.

## Bug Description

The issue occurs when attempting to access the NextAuth session within a client-side component. The `unstable_getServerSession` function returns a null session despite the user being successfully authenticated. This prevents access to user data and personalized content.

## How to Reproduce

1. Clone this repository.
2. Install dependencies: `npm install`
3. Run the development server: `npm run dev`
4. Navigate to `/about`.
5. Observe that the session object is always null, regardless of login status.

## Workaround

This solution leverages the `getServerSideProps` function to fetch the session on the server and pass it as a prop to the client-side component.

## Solution

The provided solution demonstrates how to obtain the session on the server side and pass it as a prop to the client-side component. This ensures the session is available and populated on the client, resolving the issue of null sessions.