# 0byte

> **SSL for AI content**

## About

0byte is a deep-tech studio solving the biggest problem in the generative-AI era: **“How do I know this file is real?”**  
We create open-source tooling that attaches an **invisible, zero-knowledge proof of origin** to every AI-generated image, video, or audio clip. Anyone can verify authenticity in milliseconds—no proprietary APIs, no leaked prompts, no guesswork.

**Key points**

- **One-line SDK** integrates with any AI-model pipeline.  
- **ZK-SNARK proof** binds the file hash, model, metadata, timestamp, and platform ID.  
- **On-chain anchoring** (Solana) makes the commitment immutable and public.  
- **Privacy-preserving**—we never store or reveal your prompt or weights.

---

## How it works

```mermaid
graph LR
    A[AI Platform] -->|calls| B(0byte SDK)
    B -->|upload file| C{0byte Cloud}
    C --> D[Generate ZK proof]
    D --> E[Embed proof<br/>inside media]
    E --> F[Anchor commitment<br/>on Solana]
    E -->|file + proofId| B
    B --> A
    %% Verification path
    G[Verifier] -.->|drag & drop file| H[Extract proof]
    H -.->|query| F
    H -.->|green/red| G
