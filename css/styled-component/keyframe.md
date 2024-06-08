# keyframe 활용

```typescript
const bubbleAnimation = (x: number, y: number) => keyframes`
  0% {
    opacity: 1;
    transform: translate(0, 0);
  }
  100% {
    opacity: 0;
    transform: translate(${x}rem, ${y}rem);
  }
`;

const Light = styled.span<{
  $x: number;
  $y: number;
  $size: number;
}>`
  position: absolute;
  top: 50%;
  left: 50%;
  width: ${({ $size }) => `${$size}rem`};
  height: ${({ $size }) => `${$size}rem`};
  border-radius: 50%;
  pointer-events: none;
  background-color: ${({ theme }) => theme.colors.skyBlue};

  animation: ${({ $x, $y }) => bubbleAnimation($x, $y)} 2s linear forwards;
`;
```







```typescript
const Button = styled.button`
  position: relative;
  width: 100%;
  padding: 1rem;
  background-color: ${({ theme }) => theme.colors.lightBlue};
  color: white;
  border: none;
  border-radius: 0.4rem;
  font-size: 1rem;
  font-weight: bold;
  cursor: pointer;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.2);
  z-index: 1;
`;

```







```typescript
        <Button
          type="submit"
          onMouseEnter={() => setShowBubbles(true)}
          onMouseLeave={() => setShowBubbles(false)}
        >
          로그인
          {showBubbles &&
            email &&
            password &&
            Array.from({ length: 30 }).map((_, i) => {
              const randomX = (Math.random() - 0.5) * 100;
              const randomY = (Math.random() - 0.5) * 100;
              const randomSize = Math.random() * 2 + 1;
              return (
                <Light key={i} $x={randomX} $y={randomY} $size={randomSize} />
              );
            })}
        </Button>
```
