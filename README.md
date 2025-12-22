# CodePipeline Glob Pattern Test

This repository demonstrates the glob pattern issue in AWS CodePipeline.

## Test Structure

- `apps/vivaldi/src/index.ts` - Should be IGNORED by `**/*` pattern
- `apps/vivaldi/src/config.json` - Should be IGNORED by `**/*` pattern  
- `apps/vivaldi/src/components/Button.ts` - Should be INCLUDED by `**/*` pattern
- `apps/vivaldi/src/components/types.json` - Should be INCLUDED by `**/*` pattern

## Expected Behavior
The pattern `apps/vivaldi/src/**/*.{json,ts}` should include files in subdirectories but ignore files in the root `src/` directory.

## Setup in CodePipeline
1. Create pipeline with GitHub source
2. Use the included `buildspec.yml` 
3. Check build logs to see which files are actually captured2
